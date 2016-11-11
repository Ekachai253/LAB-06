##นายเอกชัย ภมรสุขนิรนดิ์ 57030253

#ใบงานที่ 6
##เรื่อง การใช้งานคำสั่ง Console.Read() และ Console.ReadLine()
##วัตถุประสงค์
1). เพื่อให้นักศึกษาบอกชื่อ method ที่ใช้ในการรับค่าตัวอักษรพื้นฐานในภาษา C# ได้

2). เพื่อให้นักศึกษาสามารถใช้คำสั่งรับค่าตัวอักษรได้
##ความรู้เบื้องต้น
คำสั่งที่ใช้รับค่าตัวอักษรทางอินพุตมาตรฐานของ C# คือ ```Console.Read()``` และ ``` Console.ReadLine()``` โดยทั้งสองจะมีข้อแตกต่างกันคือ ```Read()``` จะอ่านตัวอักษร ส่วน ```ReadLine()``` จะอ่านสตริง จนกว่าจะกด Enter ในการรับค่าด้วย ```Read()``` และ ```ReadLine()``` จะรับเฉพาะค่า ASCII เท่านั้น หากต้องการรับค่าตัวเลข จะต้องมีการแปลง ASCII ของตัวเลขที่พิมพ์เข้ามาให้เป็นค่าตัวเลข (การรับอักษร “22” จะไม่ได้หมายถึงค่าตัวเลข 22) 

##ลำดับขั้นการทดลอง

1). สร้าง Project ตั้งชื่อเป็น Lab6 เพื่อทดลองการใช้งานคำสั่ง ```Console.ReadLine()``` และ ```Console.ReadLine()```

2). โปรแกรมสำหรับรับตัวอักษรจากคีย์บอร์ด 

  2.1). แก้ไขโปรแกรมให้เป็นดังรูป

 ![](https://github.com/Desktop-Programming-Lab-2559/LAB-06/blob/master/imgs/pic1.png)

  2.2).	โปรแกรม และบันทึกผลที่ได้
```
using System;
namespace lab6
{
    class Program
    {
        static void Main(string[] args)
        {
            char ch;
            Console.Write("Press a key folloeed by ENTER: ");
            ch = (char)Console.Read(); // get a char
            Console.WriteLine("Your key is: " + ch);
        }
    }
}
```
![](https://github.com/Ekachai253/LAB-06/blob/cb296d5dd489fd174ae03765ffffc261c23ed578/imgs/run.jpg)

#จากผลการรัน พบว่า เมื่อเราป้อนข้อมูลอะไรไป เเล้ว enter บรรทัดต่อไปมันจะนำข้อมูลที่ป้อนตำเเหน่งเเรกมาเเสดง

###คำถาม 6.1 ถ้าพิมพ์ตัวอักษรจำนวนหลายๆ ตัวแล้วกด Enter จะได้ผลอย่างไร ทำไมจึงเป็นเช่นนั้น
#ถ้าพิพม์ตัวอักษรหลายๆตัว เเล้วกดEnter ผลที่ได้มันจะเเสดงตัวอักษรตำเเหน่งเเรก ออกมา เพราะเราใช้คำสั่ง ch = (char)Console.Read(); มันจึงนำค่า ch ออกมาเเสดง

###คำถาม 6.2 ในบรรทัดที่ 11 ซึ่งมีโปรแกรมเป็น ```ch = (char)Console.Read();```  นั้น ถ้าตัด ```(char)``` ออกไป จะเกิดอะไรขึ้น ให้อธิบายประกอบ
#เกิดการ Error เนื่องจาก เราประกาศค่า ...char ch... ถ้าหากเราลบค่า (char)ออก จะทำให้เกิดการ Error

3).	โปรแกรมสำหรับรับ string จากคีย์บอร์ด
 
 3.1).	แก้ไขโปรแกรมให้เป็นดังรูป

 ![](https://github.com/Desktop-Programming-Lab-2559/LAB-06/blob/master/imgs/pic2.png)
 
 3.2).	โปรแกรม และบันทึกผลที่ได้
 ```
using System;
namespace lab6
{
    class Program
    {
        static void Main(string[] args)
        {
            string str;
            Console.WriteLine("Enter some characters.");
            str = Console.ReadLine();
            Console.WriteLine("Your key is: " + str);
        }
    }
}
```
![](https://github.com/Ekachai253/LAB-06/blob/d61cca69ad1f166af72e15f029aea761645ae7f0/imgs/run1.jpg)
#จากการรัน พบว่า เมื่อเราป้อนข้อมูล เเล้วกด enter มันจะนำข้อมูลทั้งหมดที่เราป้อนมาเเสดง

4).	โปรแกรมสำหรับรับค่าตัวเลข เนื่องจากคำสั่ง ```Read()``` และ ```ReadLine()``` จะรับเฉพาะตัวอักษร การรับตัวเลข เราต้องใช้เมธอด TryParse() มาช่วยแปลงค่า

4.1).	แก้ไขโปรแกรมให้เป็นดังรูป
 
 ![](https://github.com/Desktop-Programming-Lab-2559/LAB-06/blob/master/imgs/pic3.png)

4.2).	รัน โปรแกรม โดยป้อนตัวเลขใดๆ และบันทึกผลที่ได้
```
using System;
namespace lab6
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.Write("Please enter value 1 :");
            int val1 = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine(val1);
        }
    }
}

```
![](https://github.com/Ekachai253/LAB-06/blob/36a1e2d0f8672d9e3dedccb179bc38f64890cfdf/imgs/run2.jpg)
#จากการรันโปรเเเกรมพบว่า เมื่อป้อนตัวเลขใดๆลงไปเเล้วกดenter ค่าตัวเลขที่ป้อนก็จะเเสดงขึ้นในบรรทัดต่อไป

###คำถาม 6.3 ถ้าเราป้อนตัวอักษรลงไปแทนที่ตัวเลข จะเกิดอะไรขึ้น มีวิธีการป้องกันหรือแก้ไขอย่างไร

#เมื่อเราป้อนตัวอักษรไปเเล้วจะเกิดการดีบัก  จะเป็นดังรูปนี้
![](https://github.com/Ekachai253/LAB-06/blob/7a47ddb6141d7953705f9736c743e0cef0c76940/imgs/run3.jpg)

5).	โปรแกรมสำหรับรับค่าตัวเลข แต่ในบางกรณีที่ผู้ใช้ป้อนตัวอักษร จะทำให้เกิด error และทำให้โปรแกรม hang ได้ จึงต้องมีการป้องกันโดยใช้ประโยค ```try{…} catch{…}```  (ประโยค ```try{…} catch{…}``` นี้จะศึกษารายละเอียดภายหลัง)

  5.1).	แก้ไขโปรแกรมให้เป็นดังรูป

  ![](https://github.com/Desktop-Programming-Lab-2559/LAB-06/blob/master/imgs/pic4.png)

  5.2).	รัน โปรแกรม โดยป้อนตัวเลขใดๆ และบันทึกผลที่ได้
```
using System;
namespace lab6
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                Console.Write("Please enter value 1 :");
                int val1 = Convert.ToInt32(Console.ReadLine());
                Console.Write("Please enter value 2 :");
                int val12 = Convert.ToInt32(Console.ReadLine());
                Console.WriteLine(val1);
            }
            catch (Exception e)
            {
                Console.Write("Error :"+ e.ToString());
            }
            }
    }
}
```
![](https://github.com/Ekachai253/LAB-06/blob/db8b4c9ef44a0998c5624e9e3f977177fd01810a/imgs/run4.jpg)
#จากการรัน พบว่า เมื่อเรา ใส่ข้อมูลตัวเลข เเล้วกด enter ทั้ง Please enter value 1 เเละ Please enter value 2 จะเห็นว่าเมื่อกดenterอีกครั้งมันจะนำค่าข้อมูลตัวเลขของ Please enter value 1 ออกมาเเสดง

###คำถาม 6.4 ถ้าเราป้อนตัวอักษรลงไปแทนที่ตัวเลข จะเกิดอะไรขึ้น เหมือนหรือต่างจากโปรแกรมก่อนหน้านี้อย่างไร
#จะขึ้นว่าเราไม่สามารถ พิมพ์ตัวอักษรลงไปได้ หรือเกิดการเเจ้งเตือนการ ERROR ดังรูป
![](https://github.com/Ekachai253/LAB-06/blob/0fb7480336c93cccbc24d645d16c1d95f264ac12/imgs/run5.jpg)

##แบบฝึกหัด ให้เขียน code ในการรับค่าอินพุตต่อไปนี้และแสดงออกหน้าจอให้ถูกต้อง
``` Name :  (ป้อนชื่อของนักศึกษา). ```

``` Lastname : (ป้อนนามสกุลนักศึกษา).```

``` ID : (ป้อนรหัสนักศึกษา).```

``` GPA : (ป้อนเกรดเฉลี่ยนักศึกษา โดยมีทศนิยมสองหลัก).```
```
using System;
namespace lab6
{
    class Program
    {
        static void Main(string[] args)
        {
            try
            {
                string a1, b1, i;

                Console.Write("Name : ");
               a1 = Console.ReadLine();
                Console.Write("Lastname :");
                b1 = Console.ReadLine();
                Console.Write("ID : ");
                int A = Convert.ToInt32(Console.ReadLine());
                Console.Write("GPA : ");
                i = Console.ReadLine();
                float i1 = float.Parse(i);
                Console.WriteLine("Name : " + a1);
                Console.WriteLine("Lastname : " + a1);
                Console.WriteLine("ID : " + A);
                Console.WriteLine("GPA :{0:F2}", i1);

            }
            catch (Exception e)
            {
                Console.Write("Error :" + e.ToString());
            }
            }
    }
}
```
![](https://github.com/Ekachai253/LAB-06/blob/df0ee96b1cd7aa03070078fb22a075ac606135bf/imgs/run6.jpg)
