# View - ViewGroup

[참고 1](https://www.charlezz.com/?p=853), [참고 2](https://ktko.tistory.com/entry/ViewViewGroup-%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-View%EC%99%80-ViewGroup)

![](https://www.charlezz.com/wordpress/wp-content/uploads/2018/10/viewgroup_2x-768x336.png)

1. View : 액티비티를 구성하는 최소 단위로, 화면에 보이는 모든 것은 View라고 말할 수 있음. Widget이라고도 함.

    ex) TextView, Button, EditText, ImageView...

2. ViewGroup : 여러 개의 View를 담을 수 있는 Container, ViewGroup은 View를 상속받아 만듬. Layout이라고도 하며, LinearLayout, RelativeLayout, ConstraintLayout 등이 있음.
3. 공통 속성
    - background : View(ViewGroup)의 배경 설정
    - Visibility : View를 화면에 보여줄 것인지 보여주지 않을 것인지를 선택, VISIBLE, INVISIBLE, GONE이 있음.
    - Clickable : touch를 허용할 것(true)인지 허용하지 않을 것(false)인지 설정.
    - Focusable : View가 focus를 가질 수 있는지 설정. focus를 가진다는 뜻은 key event가 발생한 경우 그 값을 받는 상태로 만든다는 의미.
    - LayoutParmas : View(ViewGroup) 자체의 속성이 아닌, View가 배치되는 Layout에 따라 달라지는 속성들.
        - layout_width(height) : 뷰의 폭(width)와 높이(height)를 설정하는 부분. wrap_content(내부 뷰만큼 크기 맞춤)과 match_parent(부모에게 주어진 크기를 다 채움)이 있음
        - layout_gravitiy : View의 정렬 값을 의미