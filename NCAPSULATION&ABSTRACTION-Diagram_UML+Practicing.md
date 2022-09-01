# **ENCAPSULATION & ABSTRACTION**

##### ***Created by Chimmey <Đăng Huy>***

<br>

## B. ***Diagram UML + Practicing***:

<br>

## I. *Diagram UML*

- `UML`, viết tắt của *Unified Modeling Language*, là ngôn ngữ mô hình hóa thống nhất gồm các ký hiệu đồ họa được sử dụng để xây dựng và trực quan hóa các hệ thống hướng đối tượng.

- Biểu đồ của các `Class` trong `UML` là một loại biểu đồ tĩnh (*static*) mô tả cấu trúc của hệ thống bằng cách hiển thị ra:

    + Các Classes

    + Những thuộc tính của các Classes

    + Những phương thức của các Classes

    + Các mối quan hệ giữa các Objects

### 1. ***Ký hiệu lớp UML***

- Bao gồm 3 phân vùng, tương ứng với:

    + Tên của Class

    + Thuộc tính của Class

    + Phương thức của Class

![](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/03-class-notation-with-examples.png)

- Phân vùng đầu tiên:

    + Tên của Class xuất hiện trong phân vùng đầu tiên.
        
        * VD như trên: `MyClassName`.

- Phân vùng thứ hai:

    + Các thuộc tính của Class xuất hiện trong phân vùng thứ hai.

    + Loại thuộc tính được hiển thị sau dấu hai chấm.

        * VD như trên: `attribute: int`.

    + Các thuộc tính chỉ đến các biến thành viên (các data members) trong code.

- Phân vùng thứ ba:

    + Các phương thức của Class xuất hiện trong phân vùng thứ ba.
    
    + Kiểu trả về của một phương thức được hiển thị sau dấu hai chấm ở cuối.

        * VD như trên: `op1: String`.

    + Kiểu trả về của các tham số của phương thức được hiển thị sau dấu hai chấm của tên tham số.

        * VD như trên: `p1: boolean`.
    
    + Các phương thức chỉ đến các phương thức của Class trong code

<br>

### 2. ***Access Modifiers (Nhãn phạm vi) của UML***

- Các ký tự `+`, `-`, `#` trước tên của thuộc tính hoặc phương thức thể hiện phạm vi truy cập của thuộc tính hoặc phương thức đó.

![](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/04-class-attributes-with-different-visibility.png)

| Ký tự | Phạm vi truy cập | Ý nghĩa |
| :---- | :---- | :---- |
| + | public | Không hạn chế. Thành phần có thuộc tính này có thể được truy cập ở bất kì vị trí nào. |
| - | private | Thành phần có thuộc tính này sẽ chỉ được truy cập từ bên trong lớp. Bên ngoài lớp hay trong lớp dẫn xuất sẽ không thể truy cập được.|
| # | protected | Mở rộng hơn private một chút. Thành phần có thuộc tính này sẽ có thể truy cập ở trong nội bộ lớp và trong lớp dẫn xuất |

<br>

### 3. ***Hướng của tham số trong UML***

- Mỗi tham số trong một phương thức có thể được ký hiệu là `in`, `out`, `inout` chỉ định hướng của tham số đấy với phương thức gọi nó. Hướng này sẽ được viết ra trước tên tham số.

    + in: cho biết các giá trị tham số nào được caller chuyển vào.

    + out: cho biết các giá trị tham số nào được trả lại cho caller.

    + inout: cho biết các giá trị tham số nào được caller chuyển vào và sau đó được trả lại cho caller.

<br>

### 4. ***Các mối quan hệ giữa các Classes***

> Các mối quan hệ giữa các Classes qua UML:
>
> + Association
> + Inheritance
> + Realization
> + Dependency
> + Aggregation
> + Composition

<br>

a. **Cardinality**:

- Cardinality được thể hiện dưới dạng:

    + Một với một
    + Một với nhiều
    + Nhiều với nhiều

![](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/11-associations-with-different-multiplicies.png)

<br>

b. **Aggregation (Tổng hợp)**

- Là một trường hợp đặc biệt của mối quan hệ Association

    + Nó thể hiện một phần của mối quan hệ.
    + Class2 là một phần của Class1.
    + Nhiều instances (dưới dạng địa chỉ *) của Class2 có thể liên kết được với Class1.
    + Các đối tượng của Class1 và Class2 có vòng đời riêng biệt.

- Hình dưới đây cho thấy một ví dụ về tập hợp. Mối quan hệ được hiển thị dưới dạng một đường liền nét với một viên kim cương chưa được lấp đầy ở đầu kết hợp, được kết nối với lớp đại diện cho tổng thể.

![](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/12-aggregation.png)

<br>

c. **Composition (Thành phần)**

- Là một trường hợp đặc biệt của mối quan hệ Aggregation,

    + Một kiểu tập hợp đặc biệt mà các bộ phận bị phá hủy khi toàn bộ bị phá hủy.
    + Các đối tượng của Class2 sống chết với Class1.
    + Class2 không thể tự đứng.

- Hình dưới đây cho thấy một ví dụ về bố cục. Mối quan hệ được hiển thị dưới dạng một đường liền nét với một viên kim cương được lấp đầy ở đầu kết hợp, được kết nối với lớp đại diện cho toàn bộ hoặc kết hợp.

![](https://cdn-images.visual-paradigm.com/guide/uml/uml-class-diagram-tutorial/13-composition.png)

<br>

## II. *Practicing*
