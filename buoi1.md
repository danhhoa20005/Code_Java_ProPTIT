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


### 3 Access Modifiers trong Java

Access modifier (bộ điều chỉnh truy cập) trong Java xác định quyền truy cập cho các thành viên của lớp, bao gồm các biến và phương thức. Java hỗ trợ bốn loại access modifier chính:

1. **public**: Thành viên được đánh dấu là `public` có thể được truy cập từ bất kỳ đâu, bao gồm các lớp ở các package khác nhau.

2. **private**: Thành viên được đánh dấu là `private` chỉ có thể được truy cập trong cùng một lớp. Điều này giúp bảo vệ dữ liệu và ngăn không cho các lớp khác truy cập trực tiếp.

3. **protected**: Thành viên được đánh dấu là `protected` có thể được truy cập trong cùng một lớp, các lớp con (subclass), và trong cùng một package. Điều này cho phép các lớp con kế thừa và sử dụng các thành viên này.

4. **default** (không có từ khóa): Nếu không chỉ định access modifier nào, thành viên sẽ có quyền truy cập mặc định. Điều này có nghĩa là thành viên chỉ có thể được truy cập trong cùng một package.

## Ví dụ

```java
// Ví dụ về các access modifier trong Java
class AccessModifiersExample {
    public int publicVar = 10; // Có thể truy cập từ bất kỳ đâu
    private int privateVar = 20; // Chỉ có thể truy cập trong lớp này
    protected int protectedVar = 30; // Có thể truy cập trong cùng package và lớp con
    int defaultVar = 40; // Có thể truy cập trong cùng package

    public void display() {
        System.out.println("Public Variable: " + publicVar);
        System.out.println("Private Variable: " + privateVar);
        System.out.println("Protected Variable: " + protectedVar);
        System.out.println("Default Variable: " + defaultVar);
    }
}

// Lớp con trong cùng một package
class SubClass extends AccessModifiersExample {
    public void show() {
        System.out.println("Accessing variables from subclass:");
        System.out.println("Public Variable: " + publicVar);
        System.out.println("Protected Variable: " + protectedVar);
        // Không thể truy cập privateVar và defaultVar nếu không trong cùng package
    }
}

// Lớp khác trong cùng package
class SamePackageClass {
    public void access() {
        AccessModifiersExample example = new AccessModifiersExample();
        System.out.println("Accessing variables from same package:");
        System.out.println("Public Variable: " + example.publicVar);
        System.out.println("Protected Variable: " + example.protectedVar);
        // Không thể truy cập privateVar và defaultVar
    }
}

public class Main {
    public static void main(String[] args) {
        AccessModifiersExample example = new AccessModifiersExample();
        example.display();

        SubClass subClass = new SubClass();
        subClass.show();

        SamePackageClass samePackage = new SamePackageClass();
        samePackage.access();
    }
}
```

## Giải thích ví dụ

- **AccessModifiersExample**: Chứa các biến với các access modifier khác nhau.
- **SubClass**: Kế thừa từ `AccessModifiersExample` và có thể truy cập `public` và `protected` biến.
- **SamePackageClass**: Cũng nằm trong cùng một package và có thể truy cập `public` và `protected` biến.

Khi chạy chương trình, bạn sẽ thấy cách các access modifier ảnh hưởng đến khả năng truy cập của các thành viên lớp từ các lớp khác nhau.

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
