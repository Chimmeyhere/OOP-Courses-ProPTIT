# **ENCAPSULATION & ABSTRACTION**

##### ***Created by Chimmey <Đăng Huy>***

<br>

## A. ***LÝ THUYẾT***:

<br>

## I. *OBJECT ORIENTED PROGRAMMING*

> Object Oriented Programming, được hiểu là lập trình hướng đối tượng, hay còn gọi là OOP: Là một kỹ thuật lập trình dựa trên khái niệm về Class và Object. OOP tập trung vào các đối tượng thao tác hơn là logic để thao tác chúng.
> 
> Mục tiêu của OOP là tối ưu việc quản lý source code, giúp tăng khả năng tái sử dụng và quan trọng hơn hết là giúp tóm gọn các thủ tục đã biết trước tính chất thông qua việc sử dụng các đối tượng.

<br>

## II. *Vậy Class, Object là gì?*


 Trước tiên chúng ta sẽ tìm hiểu xem "Đối tượng" (Object) và "Lớp" (Class) là gì?

<!-- <br> -->

### 1. ***Object***

- Có thể lấy ví dụ để dễ hiểu rằng Object là những thứ xuất hiện xung quanh chúng ta trong thế giới thực, đó có thể là từ laptop, đến một cốc cafe,...
- Với mỗi đối tượng, thì chúng đều có những tính chất riêng khác nhau và độc lập.
  + Ví dụ:
    * Đối tượng là những chai nước, thì tính chất của chúng hoàn toàn độc lập và khác nhau. Ngoài lượng nước, nó còn bao gồm rất nhiều các thông số khác như khối lượng, màu sắc, kích cỡ, chất liệu, độ bền... Và những thông số đó chính
    * Đối tượng là chiếc điện thoại thông minh, có khả năng: chụp ảnh, nghe gọi, nhắn tin,...

- Qua 2 ví dụ trên ta có thể thấy Object có bao gồm 2 thành phần chính:

  + Thuộc tính (Attribute): Là những thông tin, đặc điểm của đối tượng.
  + Phương thức (Method): Là những hành vi mà đối tượng có thể thực hiện

- Để dễ hình dung, ta có một ví dụ thực tế về đối tượng là smartphone. Đối tượng này sẽ có:

  + Thuộc tính: màu sắc, bộ nhớ, hệ điều hành…
  + Phương thức: gọi điện, chụp ảnh, nhắn tin, ghi âm…

<br>

### 2. ***Class***

- Các Object không tự nhiên mà xuất hiện. Nó cũng được tạo ra từ khuôn mẫu có sẵn là class.

- Class bao gồm các thông tin chi tiết về các tính năng, thông số của Object bất kì mà chúng ta muốn định nghĩa. Khi định nghĩa ra một class cụ thể, có thể tạo ra hàng hằng hà sa số các Object mà chúng ta muốn.

<br>

> Class: là sự trừu tượng hóa của đối tượng. Những đối tượng có những đặc tính tương tự nhau sẽ được tập hợp thành một lớp. Lớp cũng sẽ bao gồm 2 thông tin là: thuộc tính và phương thức.

<br>

- Ví dụ với thuộc tính và phương thức như ở mục Object:
  + Thì chúng ta có các đối tượng của lớp này có thể là: Iphone, Samsung, Oppo, Huawei...

<br>

- Trong C++, để định nghĩa một lớp ta bắt đầu bằng từ khóa class, tiếp theo đó là tên của lớp và phần thân lớp được bao bởi cặp dấu {}. Kết thúc lớp bằng dấu ;

<br>

```cpp
struct NgayThang {
  int nam {}; int thang {}; int ngay {};
};
```

> Như trên là một Class ngày tháng có 3 thuộc tính: Ngày tháng năm. Và các Class bây giờ sẽ là những thời gian khác nhau trong năm

<br>

### 2. ***Con trỏ this***

- Con trỏ `this` trong Class C++ là một con trỏ đặc biệt ẩn dấu bên trong hàm thành viên của Class, có tác dụng trỏ đến đối tượng đã gọi đến hàm thành viên đó.

- Điều đó có nghĩa, khi một Object gọi tới một hàm thành viên nào đó trong Class thì con trỏ this sẽ trỏ đến vị trí của Object đó để xác định Object đang trong phiên làm việc, qua đó nó có thể giúp Object đó có thể tiếp tục truy cập và xử lý các biến thành viên có trong Class.

![](https://camo.githubusercontent.com/9eaf86c712c608819f39e57d9ce5192ca6eb488acab3a4936c569913749526b1/68747470733a2f2f6c61707472696e6863616e62616e2e636f6d2f6370702f6c61702d7472696e682d6370702d636f2d62616e2f68756f6e672d646f692d74756f6e672d74726f6e672d6370702f746869732d74726f6e672d636c6173732d6370702f736f2d73616e682d746869732d74726f6e672d6370702e706e67)

Qua ví dụ ở trên, chúng ta có thể hiểu `this` đơn giản là một con trỏ giúp xác định đối tượng nào đang gọi hàm thành viên trong Class, và chúng ta có thể lược bỏ việc viết nó trong chương trình.

Nhưng chúng ta nên sử dụng `this` trong các trường hợp chúng ta muốn phân biệt rõ giữa các biến toàn cục (glocal) và các biến thành viên chỉ sử dụng bên trong class.

## III. *4 tính chất của OOP*

> **Bao gồm:**
>  + Tính đa hình (Polymorphism)
>  + Tính kế thừa (Inheritance)
>  + Tính đóng gói (Encapsulation)
>  + Tính trừu tượng (Abstraction)

<br>

### 1. ***Tính đa hình:***

- Tính đa hình trong OOP cho phép các Object khác nhau thực thi chức năng giống nhau theo những cách khác nhau.

- Ví dụ: 
  + Ở lớp smartphone, mỗi một dòng máy đều kế thừa các thành phần của lớp cha nhưng iPhone chạy trên hệ điều hành iOS, còn Samsung lại chạy trên hệ điều hành Android.
  + Chó và mèo cùng nghe mệnh lệnh “kêu đi” từ người chủ. Chó sẽ “gâu gâu” còn mèo lại kêu “meo meo”.

<br>

### 2. ***Tính kế thừa***:

- Đây là tính chất được sử dụng khá nhiều.

- Tính kế thừa cho phép xây dựng một Class mới (Class con), kế thừa và tái sử dụng các thuộc tính, phương thức dựa trên Class cũ (Class cha) đã có trước đó. 

Các Class con kế thừa toàn bộ thành phần của Class cha và không cần phải định nghĩa lại. Class con có thể mở rộng các thành phần kế thừa hoặc bổ sung những thành phần mới.

- Ví dụ:
  + Class cha là smartphone, có các thuộc tính: màu sắc, bộ nhớ, hệ điều hành…
  + Các Class con là iPhone, Samsung, Oppo cũng có các thuộc tính: màu sắc, bộ nhớ, hệ điều hành…

<br>

### 3. ***Tính đóng gói***:

> Encapsulation:
>  + Cho phép che giấu thông tin và những tính chất xử lý bên trong của Object. Các Object khác không thể tác động trực tiếp đến dữ liệu bên trong và làm thay đổi trạng thái của Object mà bắt buộc phải thông qua các phương thức công khai do Object đó cung cấp.
>
>  + Tính chất này giúp tăng tính bảo mật cho đối tượng và tránh tình trạng dữ liệu bị hư hỏng ngoài ý muốn.

- Nhìn chung, Tính đóng gói có một số ưu điểm như sau:

  - Tính linh hoạt: Mã được đóng gói sẽ linh hoạt, dễ
 sửa đổi hơn là những đoạn mã độc lập.
  - Khả năng tái sử dụng: Mã đã đóng gói có thể được tái sử dụng trong một ứng dụng hoặc nhiều ứng dụng. Từ một đối tượng, người dùng có thể chuyển sang dùng một đối tượng khác mà không phải đổi mã. Bởi vì cả hai đối tượng đều có giao diện như nhau.

  - Khả năng bảo trì: Mã được đóng gói trong những phần riêng biệt, như là lớp, phương thức, giao diện,… Do đó, việc thay đổi, cập nhật một phần của ứng dụng không ảnh hưởng đến những phần còn lại. Điều này giúp giảm công sức và tiết kiệm thời gian cho các nhà phát triển.

  - Khả năng kiểm thử: Đối với một lớp được đóng gói, Tester sẽ diễn viết những bài kiểm thử hơn. Các biến thành viên sẽ tập trung ở một nơi chứ không nằm rải rác. Do đó, kiểm thử viên cũng tiết kiệm được thời gian và công sức hơn.

  - Che giấu dữ liệu: Khi sử dụng phương thức, người dùng chỉ cần biết nó tạo ra kết quả gì. Họ không cần quan tâm đến những chi tiết bên trong của đối tượng để sử dụng nó.

<br>

### 4. ***Tính trừu tượng***:

> Abstraction: 
>  + Tính trừu tượng giúp loại bỏ những thứ phức tạp, không cần thiết của Object và chỉ tập trung vào những gì cốt lõi, quan trọng.
  
- Ví dụ: Quản lý nhân viên thì chỉ cần quan tâm đến những thông tin như:
  + Họ tên
  + Ngày sinh
  + Giới tính
  + ...

- Thay vì quản lý thêm các thông tin như:
  + Chiếu cao
  + Cân nặng
  + Sở thích
  + Màu da
  + ...

<br>

## IV. *Nhãn phạm vi*

- Access Modifier trong một Class được sử dụng để đặt khả năng truy cập của các thành viên Class. Nó sẽ đặt ra một số hạn chế đối với các thành viên Class không được truy cập trực tiếp bởi các hàm bên ngoài.

> Có 3 loại Access Modifier được hỗ trợ bởi C++:
>- Private
>- Public
>- Protected

> **Lưu ý** rằng nếu chúng ta không hề chỉ rõ một loại Access Modifier bất kỳ nào cho thành viên của Class, thì nó tự động mặc định là Private.

| Phạm vi truy cập | Ý nghĩa |
| :---- | :---- |
| public | Không hạn chế. Thành phần có thuộc tính này có thể được truy cập ở bất kì vị trí nào. |
| private | Thành phần có thuộc tính này sẽ chỉ được truy cập từ bên trong lớp. Bên ngoài lớp hay trong lớp dẫn xuất sẽ không thể truy cập được.|
| protected | Mở rộng hơn private một chút. Thành phần có thuộc tính này sẽ có thể truy cập ở trong nội bộ lớp và trong lớp dẫn xuất |

<br>

## V. *Constructor & Destructor trong C++*

### 1. ***Constructor***:

- Một Class constructor là một hàm thành viên đặc biệt của một Class mà được thực thi bất cứ khi nào chúng ta tạo các đối tượng mới của Class đó.

- Một constructor sẽ có tên giống như Class và nó không có bất kỳ kiểu trả về, kể cả kiểu void. Constructor có thể rất hữu ích để thiết lập các giá trị khởi tạo cho các biến thành viên cụ thể.

- Một constructor mặc định trong C++ không có bất kỳ tham số nào, nhưng nếu bạn cần, một constructor có thể có các tham số.

```cpp
class Employee {
  public:
    Employee() {
        cout << "Constructor mặc định được gọi..." << endl;
    }
};
 
int main() {
    Employee e1; //tạo đối tượng Employee
    Employee e2;
    return 0;
}
```

- Với trường hợp Constructor tham số hóa, là khi Constructor được sử dụng để cung cấp các giá trị khác nhau cho các đối tượng riêng biệt.

```cpp
using namespace std;
 
class Employee {
  public:
    int id;
    string name;
    float salary;

    Employee(int i, string n, float s)
    {
        id = i;
        name = n;
        salary = s;
    }

    void display()
    {
      cout << id << "  " << name << "  " << salary << endl;
    }
};
 
int main(void) {
    // tạo đối tượng Employee
    Employee e1 = Employee(101, "Nguyen Dang Huy", 500);
    Employee e2 = Employee(102, "Ha Kieu Anh", 1000);
    e1.display();
    e2.display();
    return 0;
}
```
<br>

### 2. ***Destructor***:

- Một destructor là một hàm thành viên đặc biệt của một Class mà được thực thi bất cứ khi nào một đối tượng của Class đó ra khỏi phạm vi hoặc bất cứ khi nào biểu thức delete được áp dụng tới một con trỏ tới đối tượng của Class đó.

- Một destructor sẽ có cũng cùng tên với Class, nhưng khác với Constructor: Destructor được đặt trước bởi ký hiệu ~ và nó có thể: không trả về một giá trị và không nhận bất kỳ tham số nào.

```cpp
Employee();   // Syntax của Constructor 
~Employee();  // Syntax của Destructor
```
<br>

## VI. *Getter & Setter*

- ***Setter*** và ***Getter*** là 2 phương thức sử dụng để cập nhật hoặc lấy ra giá trị thuộc tính, đặc biệt dành cho các thuộc tính ở phạm vi `private`.

- Việc sử dụng ***Setter*** và ***Getter*** cần thiết trong việc kiểm soát những thuộc tính quan trọng mà ta thường được sử dụng và yêu cầu giá trị chính xác.

- Ví dụ thuộc tính age lưu tuổi con người, thực tế thì phạm vi tuổi là từ 0 đến 100, thì ta không thể cho chương trình lưu giá trị age âm hoặc quá 100 được.

```cpp
class Employee {
    private:
        int worktime; // Thuộc tính private
    public:
        // Setter
        void setWorkTime(int a) {
            worktime = a;
        }
        // Getter
        int getWorkTime() {
            return worktime;
        }
};
```

<br>

## VII. *Static trong Class C++*

- Static trong C++ là một toán tử có tác dụng chỉ định một biến hoặc hàm thành viên trong class tồn tại ở dạng tĩnh.

- Dạng tĩnh ở đây có nghĩa là vùng bộ nhớ dùng để lưu trữ các dữ liệu này sẽ là bất biến, không thay đổi. Đối ngược với dạng tĩnh chính là dạng động (dynamic), ví dụ như khi chúng ta tạo ra các mảng động có thể tự thay đổi kích thước chẳng hạn.

- Bằng việc sử dụng static trong class C++, chúng ta sẽ có được biến static và hàm static, là các thành viên được lưu tại các vùng bộ nhớ bất biến. Vì ở dạng tĩnh nên chúng sẽ tồn tại duy nhất trong class, và do đó chúng có thể được sử dụng chung cho tất cả các đối tượng được tạo ra từ class.

### 1. ***Biến Static***:

- Để tạo biến static trong class C++, chúng ta thêm toán tử static vào đằng trước tên biến khi khai báo biến trong class như sau. Lưu ý là access modifier của biến static phải ở dạng public để cho phép truy cập nó từ ngoài phạm vi class.

```cpp
class TestClass
{
public:    
    int num;          //Khai báo biến thông thường

    static int sNum;  //Khai báo biến static

public:
    TestClass(){ num = 10;} 
};

//Khởi tạo giá trị cho biến static
int TestClass::sNum = 100;

int main()
{   
    /*Truy cập các biến thành viên mà không tạo ra instance*/
    cout << TestClass::sNum; // 100
    cout << TestClass::num;  // error: invalid use of non-static data member
}
```

- Ưu điểm lớn nhất của biến static đó chính là chúng ta có thể sử dụng trực tiếp nó mà không cần phải tạo ra đối tượng (instance) từ class. Tuy nhiên do không tạo ra instance dẫn đến việc giá trị ban đầu của biến static cũng không được khởi tạo, nên khi dùng biến static mà không tạo ra đối tượng, chúng ta cần phải khởi tạo giá trị cho nó ở bên ngoài phạm vi class.

<br>

### 2. ***Hàm Static***:

- Để tạo hàm static trong class C++, chúng ta thêm toán tử static vào đằng trước tên hàm khi khai báo hàm trong class như sau. Lưu ý là access modifier của hàm static phải ở dạng public để cho phép truy cập nó từ ngoài phạm vi class.

```cpp
class TestClass {
public: 
    static int sNum;  // static variable
public:  
    // static member function 
    static void func1() {
        std::cout << sNum;
    } 
}; 

int TestClass::sNum = 100;

int main() 
{
    TestClass::func1(); //100
}
```

Lưu ý: đối với các hàm static có xử lý các biến thành viên, do chúng ta không tạo ra instance dẫn đến giá trị của các biến thành viên này sẽ không được khởi tạo, nên khi sử dụng chúng, bắt buộc phải có bước khởi tạo giá trị cho các biến thành viên. Và đương nhiên để làm được điều đó, các biến thành viên này cũng phải là biến static.

<br>

## VIII. *Kỹ thuật chia tách file trong C++*

> **Tại sao phải tách file?**

- Khi lưu toàn bộ code vào một file main sẽ gây ra rất nhiều vấn đề bất lợi, có thể kể đến như: Chương trình trở nên quá dài; khó quản lý, sử dụng. Giả sử ta khi muốn tìm một hàm nào đấy để chỉnh sửa thì sẽ làm tiêu tốn thời gian vì có quá nhiều hàm và không biết nó ở đâu.

- Việc tách code C++ cũng như tách code ở các ngôn ngữ khác sẽ giúp:
  + Dễ quản lí, bảo trì source code.

  + Giúp code dễ đọc, dễ hiểu và dễ sử dụng.

  + Tái sử dụng các hàm đã viết.

<br>

### ***Chia tách file (File.h & File.cpp)***:

- File.h là file để khai báo các hàm mà chương trình chúng ta cần dùng tới. Có 2 dạng: file thư viện có sẵn và file thư viện do người dùng xây dựng.

- File.cpp là file để đi định nghĩa lại các hàm đã khai báo ở file.h bên trên.

- Tương tự như include thư viện testlib, thì chúng ta sẽ include thư viện từ file.h.

```cpp
#include "file_name"
```

> Lưu ý: Cẩn thận với việc có thể trùng tên với các thư viện của C++.

- VD: chúng ta có 2 tệp, sub.cpp và main.cpp:

**sub.cpp**

```cpp
int sub(int x, int y) {
    return x - y;
}
```

**main.cpp**

```cpp
#include <iostream>
using namespace std;

int sub(int x, int y);

int main() {
    cout << "The sub of 8 and 4 is " << sub(8, 4) << "\n";
    return 0;
}
```

- Hãy viết một file header để giảm bớt gánh nặng của việc thêm thủ công cho mọi hàm bạn muốn sử dụng trong một file khác. Viết một file header rất dễ dàng, vì các file header chỉ bao gồm hai phần:

  + Các tiền chỉ thị trong file header.
  + Nội dung thực tế của file header, phải là khai báo cho tất cả các định danh mà chúng ta muốn các file khác có thể nhìn thấy.

<br>

### ***Header's file***:

<!-- <br> -->

- Các file header thường được ghép nối với các file code, với file header cung cấp các khai báo cho file code tương ứng. Vì file header của chúng ta sẽ chứa một khai báo cho các hàm được định nghĩa trong sub.cpp, nên chúng ta sẽ gọi file header mới là sub.h.

- Nếu một file header được ghép nối với một file code (ví dụ: sub.h với sub.cpp), cả hai sẽ có cùng tên (sub).

**sub.h**

```cpp
#ifndef SUB_H_
#define SUB_H_

int sub(int x, int y);

#endif
```

Để sử dụng file header này trong main.cpp, chúng ta phải #include nó *(sử dụng dấu ngoặc kép, không phải dấu ngoặc nhọn)*.

**main.cpp**

```cpp
#include <iostream>
#include "sub.h"
using namespace std;

int main() {
    cout << "The sub of 8 and 4 is " << sub(8, 4) << "\n";
    return 0;
}
```

<br>

## IX. *Quy tắc đặt tên biến trong OOP C++*

### 1. ***Đặt tên bằng tiếng anh***:

> Tên hàm hay biến đều phải đặt tên dùng bằng tiếng anh

```cpp
/* Bad */
const hoTen = "Đăng Huy"
const banBe = ["Yasuo", "Zed", "Jax"]

/* Good */
const fullName = "Đăng Huy"
const friends = ["Yasuo", "Zed", "Jax"]
```

<br>

### 2. ***Quy ước đặt tên***:

> Quy ước nào cũng được, quan trọng là consistency (tính nhất quán).

- Nếu team của bạn chọn quy ước đặt tên là `camelCase`, hãy sử dụng `camelCase` cho toàn bộ dự án, nếu bạn qua một team khác chuộng `snake_case` hơn, hãy tuân thủ nghiêm ngặt. Cho dù là quy ước nào thì điều quan trọng nhất chính là tính nhất quán.

```cpp
/* Bad */
const page_count = 5
const isUser = true

/* Good */
const pageCount = 5
const isUser = true

/* Good as well */
const page_count = 5
const is_user = true
```

<br>

### 3. ***Nguyên tắc S-I-D***:

> Nguyên tắc S-I-D:
> + Short
> + Intuitive
> + Descriptive.

- Short (ngắn gọn): tên không được dài, không phải mất thời gian để gõ và nhớ.

- Intuitive (tự nhiên): tên khi đọc lên phải cho cảm giác xuôi tai, gần gũi với văn nói.

- Descriptive (súc tích): tên phải mô tả được ý nghĩa, tác dụng của nó, bằng cách hiệu quả nhất.

```cpp
/* Bad */
const totalNumberOfPublishedArticles = 10 // tên quá dài
const a = 5 // "a" không mô tả được số 5 để làm gì
const isDisplayable = a > 5 // "isDisplayable" nghe không tự nhiên lắm

/* Good */
const totalArticles = 10
const postCount = 5
const shouldDisplay = postCount > 5
```
