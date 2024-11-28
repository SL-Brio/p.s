퀵 소트의 장점은 추가적인 공간이 필요하지 않다는 점에 있습니다. 또 그렇게 그 배열 안에서의 자리 바꿈만으로 처리가 되기 때문에 cache hit rate가 높아서 속도가 빠르다는 장점도 따라옵니다. 그렇기 때문에 우리는 추가적인 공간을 사용하지 않고 pivot을 제자리로 보낼 방법을 고민해야 합니다. 참고로 이렇게 추가적인 공간을 사용하지 않는 정렬을 In-Place Sort라고 부릅니다.

1, 2, 3, 4, 5, 6, 7, 8을 퀵 소트로 정렬하면 시간복잡도가 얼마일지 생각해봅시다. 안타깝게도 매번 선택되는 pivot은 중앙에 가는 대신 제일 왼쪽에 위치하게 되고 그로 인해 단계는 lg N개가 아닌 N개가 됩니다. 그리고 시간복잡도를 계산하면 O(N2)입니다. 퀵 소트는 최악의 경우 O(N2)입니다. 그리고 단순히 제일 왼쪽의 값을 pivot으로 선택해보면 지금처럼 리스트가 오름차순이거나 내림차순일 때에 바로 O(N2)이 됩니다.

그럼 최악의 경우 O(N2)인건 이해했는데 분명 대부분의 라이브러리에서는 퀵 소트를 쓰는 것도 사실입니다. 실제 라이브러리를 보면 다양한 처리를 하는데 피벗을 랜덤하게 택할 수도 있고, 피벗 후보를 3개 정해서 그 3개 중에서 중앙값을 피벗으로 두기도 합니다. 그리고 최악의 경우에도 O(NlgN)을 보장하기 위해서 일정 깊이 이상 들어가면 퀵 소트 대신 O(NlgN)이 보장되는 힙 소트로 정렬합니다. 이러한 정렬을 Introspective sort라고 부르고 개인적인 호기심이 있다면 찾아보셔도 좋습니다. 제가 설명한 이정도라도 알아둔다면 퀵 소트에 대해 말을 해야할 때 할 말이 더 풍부해집니다.

--만약에 직접 구현해야하면 퀵소트는 절대 쓰지말자--

--배열의 idx는 양수만 가능하다..--