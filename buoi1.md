# Tổng Quan và Cơ Bản về Java

## 1. Ngôn ngữ Java là gì?

Java là một ngôn ngữ lập trình hướng đối tượng, bậc cao, độc lập nền tảng và phổ biến rộng rãi. Nó được phát triển bởi Sun Microsystems (hiện thuộc Oracle) và chính thức ra mắt vào năm 1995. Java được thiết kế để có thể chạy trên mọi nền tảng mà không cần phải biên dịch lại, nhờ môi trường chạy máy ảo Java (JVM).

## 2. Lý do ra đời của Java

Java được tạo ra để giải quyết vấn đề phát triển phần mềm đa nền tảng. Khi máy tính và thiết bị khác nhau ngày càng phổ biến, nhu cầu về một ngôn ngữ lập trình có khả năng chạy trên nhiều loại thiết bị và hệ điều hành trở nên cần thiết. Java ra đời với khả năng "Write Once, Run Anywhere" (viết một lần, chạy mọi nơi), giúp lập trình viên tiết kiệm thời gian và công sức khi phát triển phần mềm đa nền tảng.

## 3. Cách Java hoạt động, điều gì xảy ra khi chạy code Java (.java)

Khi chạy code Java:

- **Biên dịch (Compile)**: Mã nguồn Java (.java) sẽ được biên dịch thành bytecode (.class) bởi trình biên dịch Java (javac).
- **Chạy (Execute)**: Bytecode được JVM (Java Virtual Machine) thực thi. JVM đảm bảo rằng mã có thể chạy trên bất kỳ hệ điều hành nào có cài đặt JVM mà không cần biên dịch lại.

## 4. Cấu trúc 1 chương trình Java

Một chương trình Java cơ bản gồm:

```java
public class MyProgram {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

## 5. Package là gì?

Package trong Java là một cách để nhóm các lớp liên quan lại với nhau, giúp tổ chức mã nguồn dễ quản lý và tránh xung đột tên. Ví dụ: java.util chứa các lớp tiện ích như ArrayList, HashMap.

## 6. Syntax cơ bản

**Khai báo biến nguyên thủy**
Java có các kiểu dữ liệu nguyên thủy như:

```
java
int x = 10; // Biến nguyên
double y = 5.5; // Biến số thực
boolean flag = true; // Biến boolean
char c = 'A'; // Biến ký tự
```

**Làm quen với vòng lặp**
Java hỗ trợ các loại vòng lặp như for, while, do-while:

```java
for (int i = 0; i < 5; i++) {
    System.out.println(i);
}
int j = 0;
while (j < 5) {
    System.out.println(j);
    j++;
}
```

**Câu lệnh rẽ nhánh**
Câu lệnh if-else, switch trong Java:

```java
int x = 10;
if (x > 5) {
    System.out.println("x lớn hơn 5");
} else {
    System.out.println("x không lớn hơn mã5");
}
```

```java
switch (x) {
    case 10:
        System.out.println("x bằng 10");
        break;
    default:
        System.out.println("Giá trị khác");
}
```

**Mảng trong Java**
Mảng trong Java là một cấu trúc dữ liệu cho phép lưu trữ nhiều phần tử cùng kiểu:

```java
int[] arr = {1, 2, 3, 4, 5};
for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

## 7. Tổng quan về Class và Object

**Class**:
Là một bản mẫu để tạo ra đối tượng. Class chứa các thuộc tính (biến) và phương thức (hàm) để thao tác trên các thuộc tính đó.
**Object**:
Là một thể hiện của class. Khi tạo một object, ta có thể sử dụng các phương thức và truy cập các thuộc tính của class.
Ví dụ về một class đơn giản:

```java
public class Dog {
    String name;
    int age;

    // Constructor
    public Dog(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // Phương thức in thông tin
    public void printInfo() {
        System.out.println("Tên: " + name + ", Tuổi: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Dog myDog = new Dog("Bobby", 3); // Tạo đối tượng
        myDog.printInfo(); // Gọi phương thức
    }
}
```

### 1. Từ khóa `this`

- **Ý nghĩa**: `this` là một từ khóa trong Java dùng để tham chiếu đến đối tượng hiện tại của lớp. Nó thường được sử dụng để phân biệt giữa các biến instance và các tham số của phương thức hoặc constructor.
- **Ví dụ**:

  ```java
  public class Dog {
      String name;

      public Dog(String name) {
          this.name = name; // Sử dụng this để phân biệt biến instance và tham số
      }
  }
  ```

### 2. `Constructor`

**Ý nghĩa**: Constructor là một phương thức đặc biệt được gọi khi tạo một đối tượng. Nó có cùng tên với lớp và không có kiểu trả về.
**Ví dụ**:

```java
public class Dog {
String name;

    // Constructor
    public Dog(String name) {
        this.name = name;
    }

}
```

### 3. `Access Modifier`

**Ý nghĩa**: Access modifier (các bộ điều chỉnh truy cập) xác định quyền truy cập của các thành viên lớp (biến, phương thức). Java hỗ trợ bốn loại access modifier:
public: Có thể truy cập từ bất kỳ đâu.
private: Chỉ có thể truy cập trong lớp đó.
protected: Có thể truy cập trong cùng một lớp, lớp con, và trong cùng một package.
default (không có từ khóa): Chỉ có thể truy cập trong cùng một package.
**Ví dụ**:

```java
public class Dog {
private String name; // Chỉ có thể truy cập trong lớp Dog

    public void setName(String name) {
        this.name = name; // Phương thức setter
    }

}
```

### 4. `Getter và Setter`

**Ý nghĩa**: Getter và setter là các phương thức được sử dụng để truy cập và cập nhật giá trị của các biến private trong một lớp. Chúng giúp bảo vệ dữ liệu và duy trì tính đóng gói (encapsulation).
**Ví dụ**:

```java
public class Dog {
private String name;

    // Getter
    public String getName() {
        return name;
    }

    // Setter
    public void setName(String name) {
        this.name = name;
    }

}
```

### 5. `Từ khóa static`

**Ý nghĩa**: static là một từ khóa dùng để chỉ rằng một thành viên (biến hoặc phương thức) thuộc về lớp chứ không thuộc về các thể hiện (đối tượng) của lớp. Biến static có thể được truy cập mà không cần tạo một đối tượng của lớp.
**Ví dụ**:

```java
public class Dog {
    static int count = 0; // Biến static để đếm số lượng chó

    public Dog() {
        count++; // Tăng biến count mỗi khi tạo một đối tượng Dog
    }

    public static void showCount() {
        System.out.println("Số lượng chó: " + count);
    }
}
```
