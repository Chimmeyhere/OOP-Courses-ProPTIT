# **POLYMORPHISM**

##### ***Created by Chimmey <Đăng Huy>***

<br>

## ***LÝ THUYẾT***:

<br>

## I. *Tính đa hình là gì? Vì sao cần sử dụng tính đa hình?*

- Đa hình là một trong bốn tính chất đặc trưng của lập trình hướng đối tượng bên cạnh `tính đóng gói`, `tính trừu tượng` và `tính kế thừa`. Và thường được nhắc như là trụ cột thứ ba của OOP.

- Khái niệm:
    + Đa hình (Polymorphism) có thể đơn giản hiểu là: hiện tượng mà các đối tượng thuộc các class khác nhau có thể biểu diễn cùng một thông điệp theo các cách khác nhau.
 
 <br>

- Polymorphism là một từ Hy Lạp, có nghĩa là *many-shaped* hay là *nhiều hình dạng* và nó có hai khía cạnh đặc biệt:

    + Tại thời điểm chạy, các đối tượng của lớp dẫn xuất có thể được coi là đối tượng của lớp cơ sở ở những nơi như tham số phương thức và mảng. Khi sự đa hình này xảy ra, kiểu dữ liệu của đối tượng được khai báo không còn giống với kiểu dữ liệu trong run-time của nó nữa.

    + Các lớp cơ sở có thể định nghĩa và triển khai các phương thức ảo, và các lớp dẫn xuất có thể ghi đè chúng, có nghĩa là chúng cung cấp định nghĩa và triển khai riêng. Tại thời điểm chạy, khi mã máy khách gọi phương thức, CLR sẽ tra cứu kiểu thời gian chạy của đối tượng và gọi ghi đè phương thức ảo đó. Trong mã nguồn của bạn, bạn có thể gọi một phương thức trên một lớp cơ sở và làm cho phiên bản phương thức của lớp dẫn xuất được thực thi.

<br>

Sự kế thừa trong C++ cho phép có sự tương ứng giữa lớp cơ sở và các lớp dẫn xuất trong sơ đồ thừa kế:

- Một con trỏ có kiểu lớp cơ sở luôn có thể trỏ đến địa chỉ của một đối tượng của lớp dẫn xuất.

- Tuy nhiên, khi thực hiện lời gọi một phương thức của lớp, trình biên dịch sẽ quan tâm đến kiểu của con trỏ chứ không phải đối tượng mà con trỏ đang trỏ tới: phương thức của lớp mà con trỏ có kiểu được gọi chứ không phải phương thức của đối tượng mà con trỏ đang trỏ tới được gọi.

> Ví dụ: Lớp `mayAcer` kế thừa từ lớp `Mayvitinh`, cả hai lớp này đều định nghĩa phương thức `show()`

```cpp
class Mayvitinh{  
	public: 	 	 	
	void show() {
	    cout << "mayvitinh" << endl;
	}
}; 
class mayAcer: public Mayvitinh{  	
    public: 	 	 	
    void show() {
        cout << "mayAcer" << endl;
    }
};
```

khi đó, nếu ta khai báo một con trỏ lớp `Mayvitinh`, nhưng lại trỏ vào địa chỉ của một đối tượng lớp `mayAcer`:

```cpp
mayAcer may1;
Mayvitinh *tenmay = &may1;
tenmay->show();
```

thì chương trình sẽ gọi đến phương thức show() của lớp Mayvitinh, mà không gọi tới phương thức show() của lớp mayAcer.

Để giải quyết vấn đề này, chúng ta cần sử dụng đến tính đa hình (Polymorphism) trong OOP.

<br>

- VD:
    + Một người cùng một lúc có thể có đặc điểm khác nhau. Giống như một cậu học sinh là một người con trai, một người bạn, một người anh. Vì vậy, cùng một người sở hữu những hành vi khác nhau trong các tình huống khác nhau. Điều này được gọi là đa hình.

- Đa hình được coi là một trong những tính năng quan trọng của Lập trình hướng đối tượng.

![](https://itsourcecode.com/wp-content/uploads/2022/08/Polymorphism-Example.webp)

<br>

## II. *Các loại đa hình*

> Tính đa hình chủ yếu được chia thành hai loại:
>
> + Compile time Polymorphism.
>
> + Runtime Polymorphism.

![](https://www.guru99.com/images/2/062920_1112_CPolymorphi2.png)

### ***1. Compile time Polymorphism:***

- Tính đa hình này được sử dụng bằng cách nạp chồng hàm hoặc nạp chồng toán tử.

- Một class có nhiều hàm cùng tên nhưng khác nhau về số lượng tham số hoặc kiểu dữ liệu của tham số. Khi call hàm cùng tên đó thì trong quá trình biên dịch, compiler sẽ quyết định hàm nào (trong số các hàm cùng tên) sẽ được call dựa trên số lượng tham số và kiểu dữ liệu của tham số truyển vào hàm. Việc định nghĩa các hàm cùng tên được gọi là overloading – nạp chồng hàm.

### ***2. Runtime Polymorphism:***

- Cùng một class có thể cho ra nhiều biến thể, không phải được định nghĩa bởi lớp đó, mà bởi các lớp con của nó. Đây là một phương pháp để định nghĩa lại hành vi của lớp cơ sở mà không phải sửa code của lớp cơ sở. Nếu call hàm của đối tượng của lớp dẫn xuất thông qua con trỏ của lớp cơ sở thì việc hàm nào được call sẽ được quyết định lúc Runtime. Runtime Polymorphism được thực hiện bằng phương pháp overriding – ghi đè phương thức.

***Phương thức ảo & từ khóa Virtual***

- `Virtual function` là một cách khác để triển khai tính đa hình của runtime. Nó là một hàm đặc biệt được định nghĩa trong một lớp cơ sở và được định nghĩa lại trong lớp dẫn xuất. Để khai báo một hàm ảo, bạn nên sử dụng từ khóa `virtual`. Từ khóa phải đứng trước phần khai báo của hàm trong lớp cơ sở. Nếu một lớp hàm ảo được kế thừa, lớp ảo sẽ xác định lại hàm ảo cho phù hợp với nhu cầu của nó.

Lấy ví dụ ở trên:

```cpp
#include <iostream>
using namespace std;

class Mayvitinh{  
	public: 	 	 	
	void show(){
	    cout << "mayvitinh" << endl;
	}
}; 
class mayAcer: public Mayvitinh{  	
    public: 	 	 	
    void show(){
        cout << "mayAcer" << endl;
    }
}; 

int main(){
    mayAcer may1; 
    Mayvitinh *tenmay = &may1;
    tenmay->show(); 
}
```

Sau khi biên dịch chương trình sẽ có kết quả:

```
mayvitinh
```

- Có thể thấy chương trình sau khi chạy sẽ gọi đến phương thức show() của lớp Mayvitinh, mà không gọi tới phương thức show() của lớp mayAcer.

Vậy để chương trình gọi tới phương thức show() của lớp mayAcer ta sử dụng hàm ảo virtual như sau:

```cpp
#include <iostream>
using namespace std;

class Mayvitinh{  
	public: 	 	 	
	virtual void show(){
	    cout << "mayvitinh" << endl;
	}
}; 
class mayAcer: public Mayvitinh{  	
    public: 	 	 	
    void show(){
        cout << "mayAcer" << endl;
    }
}; 

int main(){
    mayAcer may1; 
    Mayvitinh *tenmay = &may1;
    tenmay->show(); 
}
```

Sau khi biên dịch chương trình sẽ có kết quả:

```
mayAcer
```

- Trong ví dụ trên mình đã thêm từ khóa virtual vào hàm show() trong lớp cơ sở Mayvitinh.
Từ khóa virtual này dùng để khai báo một hàm là hàm ảo.

- Khi khai báo hàm ảo với từ khóa virtual nghĩa là hàm này sẽ được gọi theo loại đối tượng được trỏ (hoặc tham chiếu), chứ không phải theo loại của con trỏ (hoặc tham chiếu). Và điều này dẫn đến kết quả khác nhau:

    + Nếu không khai báo hàm ảo virtual trình biên dịch sẽ gọi hàm tại lớp cở sở

    + Nếu dùng hàm ảo virtual trình biên dịch sẽ gọi hàm tại lớp dẫn xuất

- Khi nhận thấy có khai báo virtual trong lớp cơ sở, trình biên dịch sẽ thêm vào mỗi đối tượng của lớp cơ sở và các lớp dẫn xuất của nó một con trỏ chỉ đến bảng phương thức ảo (virtual function table). Con trỏ đó có tên là vptr (virtual pointer). Bảng phương thức ảo là nơi chứa các con trỏ chỉ đến đoạn chương trình đã biên dịch ứng với các phương thức ảo. Mỗi lớp có một bảng phương thức ảo. Trình biên dịch chỉ lập bảng phương thức ảo khi bắt đầu có việc tạo đối tượng của lớp. Đến khi chương trình chạy, phương thức ảo của đối tượng mới được nối kết và thi hành thông qua con trỏ vptr.

<br>

**ĐI SÂU VÀO PHƯƠNG THỨC THUẦN ẢO Và LỚP CƠ SỞ ẢO**

#### a. ***Phương thức thuần ảo***

- Phương thức thuần ảo là 1 phương thức ảo (virtual) nhưng không có nội dung (không có thân hàm) và được khai báo bằng cách gán giá trị 0 như sau:

```cpp
#include <iostream>
using namespace std;
     
class Hinh {
	public:
	virtual void Ve() = 0;
};
     
int main() {
	// your code goes here
	return 0;
}
```

- `Lưu ý:` Chỉ có hàm ảo (có từ khóa virtual) mới được phép gán giá trị 0.

- Với ví dụ trên, chúng ta có thể thấy hàm Ve sẽ được dùng để vẽ được hình chữ nhật, hình vuông, tam giác,… nhưng ở lớp hình (class Hinh) chúng ta không có gì để vẽ ra cả.

-> Phương thức vẽ nên là phương thức thuần ảo.

- Khi sử dụng phương thức thuần ảo cần phải biết:

    + Nếu 1 lớp có 1 hoặc nhiều phương thức thuần ảo thì lớp đó được gọi là lớp cơ sở trừu tượng (abstract base class).

    + Không thể khởi tạo 1 đối tượng thuộc lớp cơ sở trừu tượng.
    
    + Nếu lớp con kế thừa từ lớp cha (với lớp cha là 1 lớp cơ sở trừu tượng) thì lớp con bắt buộc phải định nghĩa thân hàm cho hàm thuần ảo -> Nếu không làm (hoặc thiếu xót) lớp con đó sẽ được xem như là 1 lớp cơ sở trừu tượng.

- Xem rõ hơn bằng đoạn code bên dưới:

```cpp
#include <iostream>
#include <string>
using namespace std;
     
class Hinh {
	protected:
	string Ten;
	public:
	virtual void Ve() = 0;
};
     
class HinhChuNhat : public Hinh {
	public:
	HinhChuNhat() {
		Ten = "hinh chu nhat";
	}
	void Ve() {
		cout << "dang ve " << Ten << endl;
	}
};
     
class TamGiac : public Hinh {
	public:
	TamGiac() {
		Ten = "hinh chu nhat";
	}
	//Lớp tam giác không định nghĩa thân hàm Ve nên được xem như là 1 lớp cơ sở trừu tượng.
};
     
int main() {

	Hinh *hinh; //hợp lệ
    
	HinhChuNhat hcn; //hợp lệ
    
	TamGiac tamgiac; //không hợp lệ do TamGiac là lớp cơ sở trừu tượng nên ko tạo đối tượng được.
	return 0;
    }
```

<br>

#### b. ***Lớp cơ sở ảo***

- Có một vấn đề khi một lớp cơ sở được kế thừa bởi nhiều lớp dẫn xuất. Ví dụ, xét tình huống các lớp kế thừa theo sơ đồ như sau:

![](https://camo.githubusercontent.com/1371e82e9eaee07ba54ce5da37210313805c7225c3a59fc00e1147eb6af86257/68747470733a2f2f676f63686f6369742e636f6d2f77702d636f6e74656e742f75706c6f6164732f323032312f31312f736f2d646f2d6b652d746875612d7669727475616c2d626173652d636c6173732d6f6f702e706e67)

- Hai lớp B và C kế thừa từ lớp A. Lớp D kế thừa từ cả hai lớp B và C. Như vậy, lớp A được kế thừa hai lần bởi lớp D. Lần thứ nhất được kế thừa thông qua lớp B, lần thứ hai được kế thừa thông qua lớp C.

- Lúc này, nếu đối tượng của lớp D gọi đến một hàm được kế thừa từ lớp A thì sẽ gây ra một sự mơ hồ. Không biết hàm đó được kế thừa gián tiếp từ lớp B hay lớp C.

- Để giải quyết tính không rõ ràng này, C++ có một cơ chế mà nhờ đó chỉ có một bản sao của lớp A ở trong lớp D. Đó là sử dụng lớp cơ sở ảo (virtual base class).

- Sử dụng từ khóa vitual để khai báo lớp A là lớp cơ sở ảo trong các lớp B và C theo cú pháp sau:

```cpp
class A{
//Định nghĩa lớp
};
class B : virtual public A{
//Định nghĩa lớp
};
class C : virtual public A{
//Định nghĩa lớp
};
class D : public B, public C{
//Định nghĩa lớp
};
```

- Việc chỉ định A là lớp cơ sở ảo trong các lớp B và C, nghĩa là A sẽ chỉ xuất hiện một lần trong lớp D. Khai báo này không ảnh hưởng đến các lớp B và C.

`Lưu ý:` Từ khóa virtual có thể đặt trước hoặc sau từ khóa public, private, protected.

```cpp
#include <iostream>
using namespace std;

class A {
public:
    void show()
    {
        cout << "Hello from A \n";
    }
};

class B : virtual public A { //lớp cơ sở ảo
};

class C : virtual public A { //lớp cơ sở ảo
};

class D : public B, public C {
};

void main(){
	D object;
    object.show();
	system("pause");
}
```

`Virtual constructor & destructor`

- Hàm khởi tạo của một lớp cơ sở ảo luôn luôn được gọi trước các hàm khởi tạo khác.

- Hàm hủy của một lớp cơ sở ảo luôn luôn được gọi sau các hàm hủy khác.
