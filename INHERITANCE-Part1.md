# **INHERITANCE - Buổi 1**

##### ***Created by Chimmey <Đăng Huy>***

## A. ***Lý thuyết***:

<br>

## I. *Inheritance - Tính kế thừa*

### 1. ***Vậy kế thừa là gì?***:

- Thử nghĩ chúng ta có các class Asus, Dell, Lenovo đều có các
  + Attribute: Width, Height
  
  + Method: upRam()

- Khi đó, nếu chúng ta tạo các class này thì chúng ta phải viết trong mỗi lớp đều có 3 đặc điểm trên. Hơn thế nữa, nếu bạn muốn sửa lại code trong một phương thức hay một tính chất trên nào đó thì bạn phải sửa chúng cả ở 3 lớp sẽ rất tốn thời gian, và có thể dễ sai sót. Vì thế tính kế thừa sẽ được sử dụng trong trường hợp này để giải quyết vấn đề trên.

> Tính kế thừa cho phép xây dựng một Class mới (Class con), kế thừa và tái sử dụng các thuộc tính, phương thức dựa trên Class cũ (Class cha) đã có trước đó.
>
> Các Class con kế thừa toàn bộ thành phần của Class cha và không cần phải định nghĩa lại. Class con có thể mở rộng các thành phần kế thừa hoặc bổ sung những thành phần mới.

<br>

- Áp dụng tính kế thừa vào ba class trên ta sẽ tạo ra một Class Laptop có các Attribute và Method: Width, Height và upRam() với các Class con là: Class Asus, Class Dell, Class Lenovo sẽ kế thừa từ Class Laptop

![](https://i.ibb.co/KqsrCXC/oie-YCh-EV8lyj-B0s.jpg)

<br>

#### **Tính chất dẫn xuất:**

- Các Access Modifiers sau khi được kế thừa ở Class con sẽ như sau:

| | Lớp dẫn xuất | Lớp dẫn xuất | Lớp dẫn xuất |
| ---- | ---- | ---- | ---- |
| **Lớp cơ sở** | **Public Mode** | **Private Mode** | **Protected Mode** |
| Private | Không kế thừa | Không kế thừa | Không kế thừa |
| Protected | Protected | Private | Protected |
| Public | Public | Private | Protected |

<br>

### 2. ***Các loại kế thừa***

- Có tổng cộng 5 loại kế thừa:

  + Đơn kế thừa (Single Inheritance)
  
  + Đa kế thừa (Mutiple Inheritance)

  + Kế thừa đa cấp (Multilevel Inheritance)

  + Kế thừa phân cấp (Hiearchical Inheritance)

  + Kế thừa lai, Kế thừa ảo (Hybrid (Virtual) Inheritance)

- Ở buổi học này, chúng ta sẽ đi sâu vào 2 loại kế thừa là: Single Inheritance và Mutiple Inheritance.

<br>

#### a. ***Đơn kế thừa***

- `Đơn kế thừa`: là một Class chỉ được kế thừa từ đúng một Class khác. Hay nói cách khác, Class con chỉ có duy nhất một Class cha.

- VD: Class `con chó` chỉ kế thừa duy nhất từ Class `động vật`.

<br>

**Cú pháp khai báo tính đơn kế thừa:**
```cpp
class <Tên lớp dẫn xuất>: <Từ khóa dẫn xuất> <Tên lớp cơ sở> { 
    // Nội dung của Class
}; 
```

- Trong đó:

  + *Tên lớp dẫn xuất*: là tên lớp được cho kế thừa từ lớp khác. Tên lớp này tuân thủ theo quy tắc đặt tên biến trong C++.

  + *Tên lớp cở sở*: là tên lớp đã được định nghĩa trước đó để cho lớp khác kế thừa. Tên lớp này cũng tuân thủ theo quy tắc đặt tên biến của C++.

  + *Từ khóa dẫn xuất*: là từ khóa quy định tính chất của sự kế thừa. Có ba từ khóa dẫn xuất là private, protected và public.

<br>

#### **Constructor và Destructor trong đơn kế thừa**

- Thứ tự được gọi sẽ bắt đầu từ hàm khởi tạo tương ứng của lớp cơ sở, sau đó đến hàm khởi tạo của lớp dẫn xuất. Do đó, thông thường, trong hàm khởi tạo của lớp dẫn xuất phải có hàm khởi tạo của lớp cơ sở.

<br>

**Cú pháp khai báo hàm khởi tạo như sau:**

```cpp
<Tên lớp dẫn xuất>([<Các tham số>]): <Tên lớp cơ sở>([<Các đối số>]) { 
    // Khởi tạo các thuộc tính mới bổ sung của lớp dẫn xuất 
};
```

- Thứ tự gọi các hàm hủy bỏ ngược với thứ tự gọi hàm thiết lập: gọi hàm hủy bỏ của lớp dẫn xuất trước khi gọi hàm hủy bỏ của lớp cơ sở.

- Vì mỗi lớp chỉ có nhiều nhất là một hàm hủy bỏ, nên ta không cần phải chỉ ra hàm hủy bỏ nào của lớp cơ sở sẽ được gọi sau khi hủy bỏ lớp dẫn xuất. Do vậy, hàm hủy bỏ trong lớp dẫn xuất được khai báo và định nghĩa hoàn toàn giống với các lớp thông thường: 

```cpp
<Tên lớp>::~<Tên lớp>([<Các tham số>]){ 
    // giải phóng phần bộ nhớ cấp phát cho các thuộc tính bổ sung 
}
```

<br>

#### b. ***Đa kế thừa***

- `Đa kế thừa`: là một tính năng của ngôn ngữ C++. Trong đó một Class có thể kế thừa từ nhiều hơn một Class khác. Nghĩa là một Class con được kế thừa từ nhiều hơn một Class cha.

<br>

**Cú pháp khai báo tính đa kế thừa:**

```cpp
class <Tên lớp dẫn xuất>: <Từ khoá dẫn xuất> <Tên lớp cơ sở 1>, <Từ khoá dẫn xuất> <Tên lớp cơ sở 2>, <Từ khoá dẫn xuất> <Tên lớp cơ sở n> { 
    //Nội dung lớp dẫn xuất
};
```

<br>

#### **Constructor và Destructor trong đa kế thừa**

<br>

// Phần này hiện tại em chưa hiểu rõ, nên em đang muốn tìm hiểu kỹ trước khi viết kiến thức phần này vào docs ạ.

<br>

### 3. ***Hàm Friend***

- Nếu một hàm được định nghĩa là một hàm friend trong C++, thì dữ liệu `private` và `protected` của một lớp có thể được truy cập bằng cách sử dụng hàm.

**Cú pháp khai báo hàm Friend:**

```cpp
class <Tên lớp> { 
    // Khai báo các thành phần lớp như thông thường 
    // Khai báo hàm friend 
    friend <Kiểu trả về> <Tên hàm friend>([<Các tham số>]);
};
```

- Khi đó, định nghĩa chi tiết hàm bạn được thực hiện như định nghĩa một hàm tự do thông thường:

```cpp
<Kiểu trả về> <Tên hàm friend>([<Các tham số>]) { 
    // Có thể truy nhập trực tiếp các thành phần private của lớp đã khai báo 
}
```

- Đặc điểm của hàm Friend:

  + Hàm không nằm trong phạm vi của lớp mà nó đã được khai báo là friend.

  + Nó không thể được gọi bằng cách sử dụng đối tượng vì nó không nằm trong phạm vi của lớp đó.

  + Nó có thể được gọi như một hàm bình thường mà không cần sử dụng đối tượng.

  + Nó không thể truy cập trực tiếp vào tên thành viên và phải sử dụng tên đối tượng và dấu chấm toán tử với tên thành viên.

  + Nó có thể được khai báo trong phần private hoặc public.

- VD:
- 
```cpp
#include <iostream>
 
using namespace std;
 
class Box {
private:
    int length;
 
public:
    Box() : length(0) {}
    friend int printLength(Box); //ham friend
};
 
int printLength(Box b) {
    b.length += 10;
    return b.length;
}
 
int main() {
    Box b;
    cout << "Chieu dai cua box: " << printLength(b) << endl;
    return 0;
}
```

<br>

### 4. ***Function & Operator - Overloading (Nạp chồng hàm và nạp chồng toán tử)***

- Khác với `C`, thì `C++` cho phép bạn xác định nhiều hơn một định nghĩa cho một tên hàm hoặc một toán tử trong cùng phạm vi (scope), được gọi tương ứng là `Nạp chồng hàm` (Function Fverloading) và `Nạp chồng toán tử` (operator overloading) trong C++.

- Một khai báo nạp chồng là một khai báo mà đã được khai báo với cùng tên như một khai báo đã được khai báo trước đó trong cùng phạm vi, ngoại trừ cả hai khai báo có:

  + Các tham số khác nhau
  
  + Định nghĩa khác nhau.

- Khi bạn gọi `Function Overloading` hay `Operator Overloading`, thì compiler quyết định định nghĩa thích hợp nhất để sử dụng. 

  + Bằng việc so sánh các kiểu tham số bạn đã sử dụng để gọi hàm hoặc toán tử với các kiểu tham số đã được xác định trong các định nghĩa.
  
  + Tiến trình lựa chọn hàm nạp chồng hoặc toán tử nạp chồng thích hợp nhất này được gọi là `Overload Resolution` - Phân giải nạp chồng.

<br>

#### a. ***Function Overloading - Nạp chống hàm***

- Bạn có thể có nhiều định nghĩa cho cùng tên hàm trong cùng phạm vi. Định nghĩa của hàm phải khác lẫn nhau về kiểu và/hoặc số tham số trong danh sách tham số.

- `Lưu ý`: Bạn không thể nạp chồng các khai báo hàm mà chỉ khác nhau ở kiểu trả về.

- Ví dụ:

```cpp
#include <iostream>
using namespace std;
class inDuLieu
{
public:
   void hamIn(int i)
   {
      cout << "In so nguyen: " << i << endl;
   }
   void hamIn(double f)
   {
      cout << "In so thuc: " << f << endl;
   }
   void hamIn(char *c)
   {
      cout << "In ky tu: " << c << endl;
   }
};
int main(void)
{
   inDuLieu idl;
   // Goi ham hamIn de in so nguyen
   idl.hamIn(67899);
   // Goi ham hamIn de in so thuc
   idl.hamIn(6688.22);
   // Goi ham hamIn de in ky tu
   idl.hamIn("ProPTIT");
}
```

- Kết quả:

```cpp
In so  nguyen: 67899                                                  
In so thuc: 6688.22                                      
In ky tu: ProPTIT 
```

<br>

#### b. ***Operator Overloading***

- Cũng tương tự như nạp chồng hàm (Function Overloading), bạn có thể định nghĩa nhiều hàm có cùng tên, nhưng khác tham số truyền vào, nạp chồng toán tử cũng tương tự.

- Nạp chồng toán tử trong C++ là các hàm với tên đặc biệt: Tên hàm là từ khóa `operator` theo sau là ký hiệu của toán tử đang được định nghĩa. Giống như bất kỳ hàm khác, một toán tử nạp chồng có một kiểu trả về và một danh sách tham số.

- Cú pháp : **kieu_du_lieu_(tđn) operator@(const kieu_du_lieu_(tđn)&);**<br>
với @ là toán tử cần overload

- Các toán tử có thể được overload :

![](https://imgur.com/iHXVbtA.png)

- Các toán tử không thể overload:
  + Toán tử chấm (.)
  + Toán tử phạm vi (::)
  + Toán tử điều kiện (?:)
  + Toán tử sizeof

- Một số lưu ý :

  - Các toán tử một ngôi (–, ++) có thể đứng trước hoặc sau toán hạng

  - Một số toán tử có thể làm toán tử một ngôi hoặc hai ngôi như toán tử *
  - Toán tử chỉ mục ([…]) là toán tử hai ngôi
  - Các từ khóa new và delete cũng được xem là toán tử nên có thể được overload

- Cài đặt với hàm cục bộ (phương thức của lớp):

```cpp
class PhanSo {
   int tu;
   int mau;

public:
   PhanSo() : tu(0), mau(1) {}

   PhanSo operator+(const PhanSo &ps) // overload toán tử +
   {
      PhanSo kq;
      kq.tu = this->tu * ps.mau + ps.tu * this->mau;
      kq.mau = this->mau * ps.mau;
      return kq;
   }
};
```
- Cài đặt với hàm toàn cục (dùng hàm friend) :

```cpp
class PhanSo {
   // properties & methods
   friend PhanSo operator+(const PhanSo &ps, const int &i);
}

PhanSo operator+(const PhanSo &ps, const int &i)
{
   PhanSo kq;
   kq.tu = ps.tu + i * ps.mau;
   return kq;
}
```

<br>

### 5. ***Function Overiding (Ghi đè)***

- Nếu lớp dẫn xuất định nghĩa cùng một phương thức đã được định nghĩa trong lớp cơ sở của nó, nó được gọi là phương thức ghi đè trong `C++`. Phương thức ghi đè được sử dụng để đạt được tính đa hình của OOP. Phương thức ghi đè cho phép bạn cung cấp việc thực hiện cụ thể chức năng đã được lớp cơ sở của nó cung cấp.

- Overriding thường được sử dụng trong method ở lớp con.

- `Lưu ý`:

  + Các phương thức được mô tả static thì không được Overriden nhưng được mô tả lại.

  + Các phương thức không kế thừa sẽ không được Overriden (hiển nhiên).

- VD của Function Overiding:

```cpp
class Animal
{
public:
   void eat()
   {
      cout << "Eating...";
   }
};
class Dog : public Animal
{
public:
   void eat()
   {
      cout << "Eating bread...";
   }
};
int main(void)
{
   Dog d = Dog();
   d.eat();
}
```

```cpp
Kết quả :

Eating bread...
```
