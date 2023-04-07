## 셀 재사용

- 셀을 왜 재사용해야할까요?
    - 저희는 collectionView 또는 tableView를 사용하면서 cell을 재사용한다는 것을 알게되었습니다.
    - 그 이유는 여러분들도 알다시피 메모리를 아껴주기 위해서입니다.
    - Cell이 재사용되는 과정을 밑의 사진처럼 볼 수 있습니다.
    - Queue에서 Cell을 보존하고, prepareForReuse와 cellForItemAt으로 특정 indexPath의 cell을 초기화해주죠. 그리고 화면에서 벗어나면 다시 queue에 보내지게됩니다.
        
        ![image](https://user-images.githubusercontent.com/76683388/230541328-a6c629d3-ebce-49cd-a024-62284eed0c1d.png)


## 셀 라이프 사이클

---

- 그럼 자세한 셀의 생명주기를 살펴보겠습니다.
- 자료 출처는 wwdc 16 what`s new in UICollectionView in iOS10 입니다.
![Untitled](https://user-images.githubusercontent.com/76683388/230541466-f14f7a67-07c5-4ced-a26f-d1afbfd68bb8.png)

- prepareForReuse가 호출되어 Cell이 초기화됩니다.
![2](https://user-images.githubusercontent.com/76683388/230541471-9020b690-b226-4088-825d-295ba6c1602e.png)

- cellForItemAtIndexPath 가 호출되어 Cell 내부에 데이터를 채웁니다.
![3](https://user-images.githubusercontent.com/76683388/230541486-f9a63da1-62b5-404e-af68-a28b3db7abbf.png)
![4](https://user-images.githubusercontent.com/76683388/230541492-d47164af-20a7-4296-a737-e2901a06aa3b.png)

- Cell이 뷰로 올라가기 바로 직전 willDisplayCell이 호출됩니다.
![5](https://user-images.githubusercontent.com/76683388/230541497-0906e125-45e8-4bd8-9c62-5d5d9a6fbbb2.png)

- Cell이 화면밖으로 나가면 didEndDisplayingCell이 호출됩니다.
![6](https://user-images.githubusercontent.com/76683388/230541502-352ef0a3-5279-4ca1-aecf-0a7a3a5224e5.png)

- 화면밖으로 나간 Cell이 밖으로 나간다고 바로 reuse Queue로 가지 않습니다.
![7](https://user-images.githubusercontent.com/76683388/230541512-399b9455-6358-43a5-8ad3-664a714585a9.png)

- 만약 다시 스크롤을 통해 Cell이 보여진다면 prepareReuse부터 하지않고 바로 Cell을 보여줍니다.

### WWDC 20 셀 생명주기
![8](https://user-images.githubusercontent.com/76683388/230541522-bbb01bf4-2f33-4210-ab5d-b41b588fb34c.png)

## 셀 재구성

---

- iOS15 부터 생긴 기능에 대해 말씀드리려합니다.
- iOS15 이전에는 위에 셀의 생명주기처럼 Cell이 나타나기까지 prepareForReuse 호출, cellforItemAt 호출, 그다음 표시 등이 이루어졌습니다.
- 하지만 iOS15 부터는 CellForItemAt 함수가 업데이트 되었습니다.

    ![9](https://user-images.githubusercontent.com/76683388/230541532-3150988a-e573-4cb0-9810-ac819a304b94.png)
    ![10](https://user-images.githubusercontent.com/76683388/230541644-ae4e952d-02f2-4d6c-8c61-558249038344.png)

    
    
- iOS15 이전에는 indexPath의 범위를 벗어나거나 cell이 보이지않으면 nil을 반환했습니다. 예외로 당장 didEndDisplay되고 아직 reuse Queue로 가기 전 상태인 Cell은 빼고요.
- iOS15 이후부터는 indexPath에 prepare된 cell이 있다면 Cell을 load하지않고 reconfigure를 한다고 합니다.
- 이게 무엇이냐.
- 우리는 dequeueReusable을 통해 계속해서 Cell을 초기화 해주는 과정을 밟았습니다. 하지만 이미 prepared된 Cell이 있다면 Cell을 초기화해주는 과정없이, Cell을 바로 가져와서 쓴다고 합니다.
- 이때 reuse cell에서 indexPath에 해당하는 cell을 빼주고 기존 cell을 반환해준다고합니다.
- 이로인해서 Cell을 새로 load 하는 것보다 효율적인 효과를 볼 수 있습니다.
