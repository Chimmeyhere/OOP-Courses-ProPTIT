# [**Object Oriented Programming (OOP)**](https://github.com/monkeydminh49/PTIT/blob/master/Theory.md)

## **Object Oriented Programming là gì?**

- **Lập trình hướng đối** tượng (Object Oriented Programming, viết tắt: OOP) là một kỹ thuật lập trình cho phép lập trình viên tạo ra các **_đối tượng_** trong code trừu tượng hóa các **_đối tượng thực tế trong cuộc sống_**.

- **Đối tượng (Object)** có thể là con người, điện thoại, máy tính và điểm chung là đều gồm 2 thành phần chính là:

  - **Thuộc tính (Attribute)**: là những thông tin, đặc điểm của đối tượng.
  - **Phương thức (Method)**: là những hành động mà đối tượng có thể thực hiện.

- Khi một đối tượng có những đặc tính như nhau sẽ được gom lại thành một **lớp đối tượng (class)** và cũng sẽ có 2 thành phần là **thuộc tính** và **phương thức**. **Lớp (class)** cũng có thể được dùng để định nghĩa một kiểu dữ liệu mới.

Với ví dụ máy vi tính trên ta hiểu **lớp (class)** máy vi tính có:

Các **thuộc tính** như: màu sắc, kích thước, bộ nhớ, ...
Và các **phương thức** như: quét virus, tắt máy, khởi động máy, ...

- **Con trỏ this** trong class là một con trỏ đặc biệt ẩn dấu bên trong hàm thành viên của class, có tác dụng trỏ đến đối tượng đã gọi đến hàm thành viên đó.
  - Điều đó có nghĩa, khi một đối tượng gọi tới một hàm thành viên nào đó trong class thì con trỏ this sẽ trỏ đến vị trí của đối tượng đó để xác định đối tượng đang trong phiên làm việc, qua đó nó có thể giúp đối tượng đó có thể tiếp tục truy cập và xử lý các biến thành viên có trong class.

## **Bốn tính chất của lập trình hướng đối tượng**

1. Tính đóng gói (Encapsulation): Tính chất này không cho phép người dùng trực tiếp tác động đến dữ liệu bên trong đối tượng mà phải thông qua các phương thức mà đối tượng cung cấp. Tính chất này đảm bảo tính toàn vẹn của đối tượng.

   Một ví dụ về tính đóng gói:

   ```c++
   class mayvitinh {
   private:
       string mausac;
       int chieudai, chieurong;
   public:
       void input()
       {
           cout << "Nhap mau sac may: ";
           fflush(stdin);
           getline(cin, this->mausac);
           cout << "Nhap chieu dai may: ";
           cin >> this->chieudai;
           cout << "Nhap chieu rong may: ";
           cin >> this->chieurong;
       }

       void output()
       {
           cout << "Mau sac may: " << this->mausac <<  endl;
           cout << "Chieu dai may: " << this->chieudai     << endl;
           cout << "Chieu rong may: " <<   this->chieurong << endl;
       }
   };
   ```

   - Trong đoạn code trên **tính đóng gói** được thể hiện qua các **thuộc tính** mausac, chieudai, chieurong và **phương thức** input(), output() vào trong class mayvitinh. Bạn không thể truy cập đến các private data hoặc gọi đến private methods của class từ bên ngoài class đó.

2. Tính kế thừa (Inheritance): Kế thừa, tái sử dụng phương thức, thuộc tính của lớp cơ sở và lớp kế thừa được gọi là lớp con, nó sẽ thừa hưởng những gì lớp cha có và cho phép.

3. Tính đa hình (Polymorphism): Tính đa hình cho phép các chức năng (method) khác nhau được thực thi khác nhau trên các đối tượng khác nhau.

4. Tính trừu tượng(Abstraction): Tập trung vào cốt lõi của đối tượng, bỏ qua những thứ không liên quan và không quan trọng.

   Ví dụ: Bài toán quản lý sinh viên chúng ta chỉ cần quản lý các thông tin như

   - Họ tên
   - Ngày sinh
   - Giới tính
   - …

   mà lại không cần quản lý thêm các thông tin:

   - Cân nặng
   - Màu da
   - Chiều cao

   Tại vì chúng thực sự không cần thiết.

## **Access Modifiers (Nhãn phạm vi)**

Các loại phạm vi truy cập và ý nghĩa

| Phạm vi truy cập | Ý nghĩa                                                                                                              |
| ---------------- | -------------------------------------------------------------------------------------------------------------------- |
| public           | Không hạn chế. Thành phần mang thuộc tính này có thể được truy cập ở bất kì nơi nào.                                 |
| private          | Thành phần mang thuộc tính này là thành phần riêng tư **chỉ** có nội bộ bên trong lớp chứa nó mới có quyền truy cập. |
| protected        | Tương tự **private** ngoài ra còn có thể truy cập từ lớp dẫn xuất lớp chứa nó.                                       |

## **Các hàm cơ bản trong OOP**

1. **Constructor (Hàm khởi tạo):**

   - **Hàm khởi tạo** là một hàm đặc biệt trong lớp. Hàm này được gọi tự động khi một đối tượng được tạo ra. Hàm khởi tạo sẽ khởi tạo giá trị cho các thuộc tính của đối tượng. Trong C++, một hàm khởi tạo có đặc điểm sau:

     - Tên hàm khởi tạo trùng với tên của lớp.

     - Hàm khởi tạo không có kiểu dữ liệu trả về (kể cả void).

     - Hàm khởi tạo phải được khai báo với phạm vi truy cập là public.

     - Hàm khởi tạo có thể có đối số hoặc không có đối số.

     - Trong một lớp có thể có nhiều hàm khởi tạo (cùng tên nhưng khác đối số).

   Ví dụ:

   ```c++
    class Circle{
      private:
        float r;
     public:
       //Hàm khởi tạo không có tham số (Hàm khởi tạo mặc định (default constructor))
       Circle(){
           this->r = 1.0;
       }
       //Hàm khởi tạo có tham số
       Circle(float r){
           this->r = r;
       }
       void setRadius(float r){
           this->r = r;
       }
       float getRadius(){
           return r;
       }
       float calculateArea(){
           return 3.14 * r * r;
       }
   };
   ```

2. **Destructor(Hàm hủy)**

   - Hàm huỷ sẽ **tự động được gọi** trước khi giải phóng một đối tượng để giải phóng vùng nhớ trước khi đối tượng được hủy bỏ. Hàm hủy có các đặc điểm sau:

     - Mỗi lớp chỉ có một hàm hủy.

     - Hàm hủy không có kiểu, không có giá trị trả về và không có đối số.

     - Tên hàm huỷ cùng tên với tên lớp và có một dấu ngã (~) ngay trước tên.

   Ví dụ:

   ```c++
   #include <iostream>
   using namespace std;

   class Circle{
     private:
       float r;
     public:
       //Hàm khởi tạo có tham số
       Circle(float r){
           this->r = r;
       }
       void setRadius(float r){
           this->r = r;
       }
       float getRadius(){
           return r;
       }
       float calculateArea(){
           return 3.14 * r * r;
       }
       ~Circle(){
           cout<<"Radius of circle has     destroyed."<<endl;
       }
   };

   void main()
   {
       Circle c1(3.5);
       cout<<"Area of Circle = "<<c1.  calculateArea();
   }
   ```

   Kết quả:

   ```txt
   Area of Circle = 38.465
   Radius of circle has destroyed.
   ```

3. **Getter và setter:**

   - **Setter** và **Getter** là 2 phương thức sử dụng để cập nhật hoặc lấy ra giá trị thuộc tính, đặc biệt dành cho các thuộc tính ở phạm vi **private**.

   Cú pháp:

   Setter

   ```c++
   public void set<tên thuộc tính>(<tham số giá trị mới>) {

       this.<tên thuộc tính> = <tham số giá trị mới>;
   }
   ```

   Getter

   ```c++
   <kiểu dữ liệu thuộc tính> get<tên thuộc tính> () {

     return this. <tên thuộc tính>;

   }
   ```

## **Biến static**

- Biến static trong Hàm: Khi một biến được khai báo với từ khóa static, vùng nhớ cho nó tồn tại theo vòng đời của chương trình. Ngay cả khi hàm được gọi nhiều lần, vùng nhớ cho biến static chỉ được cấp nhát một lần và giá trị của biến trong những lần gọi trước đó được lưu lại và được sử dụng để thực hiện thông qua các lượt gọi hàm tiếp theo. Điều này rất hữu ích để triển khai các ứng dụng nào khác mà trạng thái chức năng trước đó cần được lưu trữ.

Ví dụ:

```c++
#include <iostream>
#include <string>

using namespace std;

void demo()
{
    static int count = 0;
    cout << count << " ";

    count++;
}

int main()
{
    for (int i=0; i<5; i++)
        demo();
    return 0;
}

```

Kết quả:

```txt
0 1 2 3 4
```

- **Các biến static trong class:** Vì các biến được khai báo là tĩnh chỉ được khởi tạo một lần khi chúng được cấp phát một địa chỉ trong bộ lưu trữ tĩnh riêng biệt, do đó, các biến tĩnh trong một lớp được chia sẻ bởi các đối tượng. Chúng ta không tạo ra các bản sao cho cùng một biến tĩnh của các đối tượng khác nhau. Cũng vì lý do này mà các biến tĩnh không thể được khởi tạo bằng cách sử dụng các hàm khởi tạo (hàm constructor()).

```c++
#include<iostream>
using namespace std;

class GfG
{
   public:
     static int i;

     GfG() {  };
};

int main()
{
  GfG obj1;
  GfG obj2;
  obj1.i =2;
  obj2.i = 3;

  cout << obj1.i<<" "<<obj2.i;
}
```

--> Chương trình lỗi, không chạy được.

- Một biến static bên trong một class nên được khởi tạo bằng cách sử dụng toán tử tên và toán tử phân giải phạm vi bên ngoài class như dưới đây:

```c++
#include<iostream>
using namespace std;

class GfG
{
public:
    static int i;

    GfG() {};
};

int GfG::i = 1;

int main()
{
    GfG obj;
    cout << obj.i;
}
```

Kết quả:

```txt
1
```

## **Kỹ thuật chia tách file (file.h và file.cpp)**

### **Tại sao phải tách file?**

- Khi lưu toàn bộ code vào một file main sẽ gây ra rất nhiều vấn đề bất lợi, có thể kể đến như: Chương trình trở nên quá dài; khó quản lý, sử dụng. Giả sử ta khi muốn tìm một hàm nào đấy để chỉnh sửa thì sẽ làm tiêu tốn thời gian vì có quá nhiều hàm và không biết nó ở đâu.

- Việc tách code C++ cũng như tách code ở các ngôn ngữ khác sẽ giúp:
  - Dễ quản lí, bảo trì source code.
  - Giúp code dễ đọc, dễ hiểu và dễ sử dụng.
  - Tái sử dụng các hàm đã viết.

### **Tách code C++ như thế nào?**

- Việc tách code c++ là từ một file chứa đầy đủ khai báo các hàm và định nghĩa của chúng ta, tách thành 2 file:
  - file.h để khai báo các hàm
  - file.cpp để định nghĩa các hàm đã khai báo trong file.h

Ví dụ:

**GradeBook.h:**

```c++
// GradeBook class definition. This file presents GradeBook's public
// interface without revealing the implementations of GradeBook's member functions, which are defined in GradeBook.cpp.
#include <string>  // class GradeBook uses C++ standard string class

// GradeBook class definition
class GradeBook {
   public:
    GradeBook(std::string nameOfCourse, std::string nameOfInstructor);
    void setCourseName(std::string);
    std::string getCourseName() const;
    void setInstructorName(std::string);
    std::string getInstructorName() const;
    void displayMessage() const;

   private:
    std::string courseName;
    std::string instructorName;
};
```

**GradeBook.cpp:**

```c++
#include "GradeBook.h"

#include <iostream>
using namespace std;

GradeBook::GradeBook(string nameOfCourse, string nameOfInstructor)
    : courseName(nameOfCourse),
      instructorName(nameOfInstructor) {
}

void GradeBook::setCourseName(string name) {
    courseName = name;
}

string GradeBook::getCourseName() const {
    return courseName;
}

void GradeBook::setInstructorName(string name) {
    instructorName = name;
}

string GradeBook::getInstructorName() const {
    return instructorName;
}

void GradeBook::displayMessage() const {
    cout << "Welcome to the grade book for \n"
         << getCourseName()
         << "!\n"
         << "This course is presented by: "
         << getInstructorName() << endl;
}
```

## **Quy tắc đặt tên biến trong OOP C++**

1. **Lớp (class)**

   - Các lớp là các danh từ được viết bằng chữ cái đầu tiên viết hoa, như Person, Account, hoặc Task.

2. **Các đối tượng (objects)**

   - Tên biến đối tượng phải phù hợp với tên lớp liên quan (đối tượng person là của lớp Person, đối tượng account của lớp Account, v.v.). Bạn cũng có thể tự do sử dụng tính từ cho tên đối tượng (ví dụ: completedTask). Điều quan trọng là phải giữ nguyên tên lớp là phần cuối cùng của tên đối tượng.

3. **Đặt tên hàm tham số**

   - Các hàm tham số hoạt động tương tự như các biến bên trong một hàm. Tuy nhiên, có hai trường hợp ngoại lệ: phương thức khởi tạo và phương thức setter. Với hai loại này, nên sử dụng tiền tố hoặc hậu tố cho một tên biến:

   ```c++
   class Person{
    private:
        string name;
        string address;

    public:
       Person(string newName, string newAddress) {
           name = newName;
           address = newAddress;
       }
       void setName(final Name newName) {
           name = newName;
       }
   }

   ```

4. **Các hằng bất biến**
    - Các hằng số bất biến tĩnh là một trường hợp đặc biệt nên hãy tên cho các biến không sử dụng tất cả các chữ viết hoa như kiểu. Ví dụ:
    <mark>TOOLTIP_SHOW_DELAY_IN_MILLISECS</mark>.
