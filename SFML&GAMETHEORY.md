# **SFML & GAME THEORY**

##### ***Created by Chimmey <Đăng Huy>***

<br>

## I. *Thư viện đồ họa*

- Trong khóa Game C++, chúng ta sẽ được học và sử dụng thư viện đồ họa để thực thi các tác vụ về đồ họa, âm thanh,... cho trò chơi của mình. Sẽ có những thư viện đồ họa như SFML, Cocos2d, SDL,... Nhưng chúng ta sẽ tập trung vào thư viện đồ họa `SFML`.

- `SFML` được viết bằng C++, và dựa trên nền tảng OpenGL để render hình ảnh.

- `SFML` gồm 5 module:

    + System
    + Window
    + Graphics
    + Audio
    + Network

- Window Module cho phép chúng ta mở và vận hành một cửa sổ OpenGL của Game.

- Graphics Module cho phép chúng ta vẽ và thiết kế các khối hình, chữ, sprites, textures, shaders,... qua nhiều đặc điểm như kích thước, vị trí, góc nghiêng, góc nhìn của Game.

- Audio Module cho phép chúng ta sử dụng nhạc, hiệu ứng âm thanh cho Game.

- Link tài liệu tham khảo SFML: https://www.sfml-dev.org/tutorials/2.5/

<br>

## II. *About Game*

### 1. ***Game 2D và các thể loại game***

- Trong khóa Game C++, chúng ta sẽ sử dụng kiến thức lập trình hướng đối tượng để tạo nên một Game 2D bằng thư viện đồ họa SFML, SDL, Cocos2d,...

> VẬY GAME 2D LÀ GÌ?
> 
> - Game 2D là trò chơi sử dụng đồ họa phẳng, được gọi là sprites, không hề có hình học không gian 3 chiều. Chúng được vẽ trên màn hình dưới dạng hình ảnh phẳng và sẽ không thể thay đổi góc nhìn.
>
> - Game 2.5D là một trường hợp đặc biệt cho Game 2D, đây là khi mà Game 2D sử dụng hình học 3 chiều cho môi trường và nhân vật, nhưng hạn chế lối chơi ở hai chiều, ví dụ: góc nhìn có thể hiển thị chế độ xem cuộn bên, nhưng người chơi chỉ di chuyển theo hai chiều. Đối với loại trò chơi này, hiệu ứng 3D có mục đích trực quan hơn là chức năng.

![](https://cdn.mos.cms.futurecdn.net/bmENCEixSvPhDaMLnKzrKm.jpg)

![](https://i0.wp.com/d9n64ieh9hz8y.cloudfront.net/wp-content/uploads/20161027161512/stardew-valley-2.jpg?resize=1280%2C720&ssl=1)

![](https://ecdn.game4v.com/g4v-content/uploads/2021/08/Game4V-HOA-00.jpg)

> CÓ NHỮNG THỂ LOẠI GAME NÀO? - Theo thị trường game hiện tại, ta có thể chia thành 10 thể loại game thịnh hành nhất hiện nay.
> 
> - Sandbox
>
> - Real-time strategy (RTS)
> - Shooters (FPS and TPS)
> - Multiplayer online battle arena (MOBA)
> - Role-playing (RPG, ARPG, and More)
> - Simulation and sports
> - Puzzlers and party games
> - Action-adventure
> - Survival and horror
> - Platformer

- Sandbox:
![](https://cdn.sforum.vn/sforum/wp-content/uploads/2022/05/cach-tai-xuong-va-choi-minecraft-tren-chromebook-e1646810034525.jpg)

- Real-time strategy:
![](https://1.bp.blogspot.com/-kGcukY3G0og/XovasEDZfBI/AAAAAAAABVs/oPaEGjawA3MjKiUB7kDOd_9rOehCr7EnQCLcBGAsYHQ/s640/2020-04-07_8-42-21.jpg)

- Shooters:
    + FPS:
    ![](https://cdn.hubs.vn/pv-blog/2020/04/Valorant-phong-vu-2.jpg)

    + TPS:
    ![](https://assets-prd.ignimgs.com/2022/01/21/snapshot-103-1642723335779.png)

- MOBA:
![](https://en.number13.de/content/images/2021/05/hecarim-ultimate.jpg)

- Role-playing:
![](https://gamingbolt.com/wp-content/uploads/2014/06/The_Witcher_3_Wild_Hunt_The_world_of_The_Witcher_3_just_begs_to_be_explored.jpg)

- Simulation and sports:
![](https://i.ytimg.com/vi/qC9KSW8IhLQ/maxresdefault.jpg)

- Puzzlers and party games:
![](https://s3.amazonaws.com/tetris-www1/assets/article/2017/07/21/tetris-challenges_feature.jpg)

- Action-adventure:
![](https://assets.reedpopcdn.com/ac_2_002.png/BROK/resize/3840x3840%3E/format/jpg/quality/100/ac_2_002.png)

- Survival and horror:
![](https://cdn.vox-cdn.com/uploads/chorus_asset/file/13695830/Resident_Evil_2_intro_0011_Layer_5.jpg)

- Platformer:
![](https://thetriangle.org/wp-content/uploads/2017/10/Cuphead-1.jpg)

<br>

### 2. ***Lý thuyết Game cơ bản***

a. **Game loop**

- Vòng lặp này thường được gọi là `Game loop` vì nó kiểm soát thời gian tồn tại của ứng dụng. Miễn là cái này tiếp tục lặp lại, ứng dụng sẽ vẫn tồn tại. Trong trường hợp chúng ta muốn dừng chương trình, chúng ta muốn ứng dụng của mình chấm dứt thực thi ngay khi cửa sổ không còn tồn tại.

- Bây giờ chúng ta làm gì trong một lần lặp lại của vòng lặp này? Đầu tiên, chúng ta xử lý các sự kiện từ cửa sổ, sau đó chúng ta cập nhật trò chơi và cuối cùng chúng tôi hiển thị kết quả trên màn hình. Sự lặp lại của vòng lặp trò chơi thường được gọi là một khung hình. Và từ đó chúng ta có khái niệm về FPS (khung hình / giây).

![](https://static.packt-cdn.com/products/9781849696845/graphics/6845_01_02.jpg)

<br>

b. **Delta time**

- `Delta time` là thời gian cần để hiển thị khung hình. Nói cách khác Delta time là khoảng thời gian giữa khung hình cuối cùng và khung hình hiện tại.
    + Delta có nghĩa là "sự khác biệt"

- `Delta time` được sử dụng để ngăn hiện tượng nhân vật di chuyển không được mượt trên các máy mạnh yếu khác nhau

- Tất nhiên, hiếm khi các trò chơi chạy ở FPS ổn định. Nhưng khi tốc độ khung hình thay đổi, delta time cũng vậy. Khi có sự sụt giảm FPS đột ngột thì cả giây trôi qua cho đến khung hình tiếp theo, delta time trong khung hình tiếp theo đó sẽ là 1 giây trên mỗi khung hình - chứ không phải 0.02 như lúc bình thường nữa.

- Sau khi lag, thay vì thêm speed * 0.02 vào vị trí của ô tô, trò chơi sẽ thêm speed * 1, hoặc 0,2. Trước mắt bạn, chiếc xe có vẻ như sẽ tốc biến về phía trước sau cú drop FPS đó, nhưng đó là cách nó sẽ di chuyển nếu sự giảm đột ngột FPS trên chưa bao giờ xảy ra và bạn sẽ không bị tụt lại phía sau.

<br>

c. **Sprites và textures**

- `Sprites` và `Textures` đều là những hình ảnh.

- `Sprite` là một hình ảnh có thể được sử dụng như một đối tượng 2D, có tọa độ (x, y) và bạn có thể di chuyển, phá hủy hoặc tạo ra trong trò chơi.

- Một `Texture` cũng là một hình ảnh, nhưng nó sẽ được sử dụng để thay đổi sự xuất hiện của một đối tượng. Ví dụ: bạn có thể thiết lập một kết cấu cho các mặt của một khối lập phương, một lớp (như nền) hoặc thậm chí một sprite. Nhưng vì kết cấu không phải là vật thể, bạn không thể di chuyển chúng trong suốt trò chơi.

<br>

d. **Animation**

- Về lý thuyết, cơ chế chuyển động của `Animation` là một chuyển động được tạo bởi nhiều hình ảnh khác nhau trong cùng một khung hình, nối tiếp nhau thành một chuỗi hình ảnh. Khi đó sẽ tạo thành ảo ảnh thị giác về chuyển động trong khoảng thời gian nhất định.

- `Game Animation` là tạo ra các chuỗi hành động cho nhân vật và các đối tượng nhờ cơ chế của `Animation`.
