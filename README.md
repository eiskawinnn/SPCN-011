# SPCN-011

1.เลือก Creat Virtual Machine 

2.กรอกรายละเอียดชื่อและตั้งค่าต่างๆ

      -ตัวอักษรชื่อภาษาอังกฤษตัวเอง  3 ตัว - เลข VM ID                                                                              
      -ช่อง Resource Pool เลือก Special_CN
      -ช่อง ISO image เลือก ubuntu-22.04.1-live-server-amd64
      -System ตั้งค่าตามค่า default 
      -Disk ตั้งค่าตามค่า default 
      -CPU ตั้งค่าตามค่า default
      -Memory เลือกค่า 2048
      -Netwoek ตั้งค่าตามค่า default
      
![image](https://user-images.githubusercontent.com/117457616/208311225-f371a262-2994-46f8-90ce-5ee23fd4d18c.png)

3.Install ตามขั้นตอน และจะมีให้กรอกข้อมูล

4.ตั้งค่า SSH เลือก Github ใส่รายละเอียด Username Github Confirm SSH Keys แล้วรอติดตั้ง
![image](https://user-images.githubusercontent.com/117457616/208311271-e6647a06-710e-4c3e-bd13-0bdf086b1cde.png)

Setup timezone

-ใช้คำสั่ง เพื่อตั้งค่าเวลา

      Sudo timedatectl set-timezone Asia/Bankok
      
-ใช้คำสั่ง เพื่อเช็คเวลา

      date
      
ติดตั้ง QEMU Guest Agent

![image](https://user-images.githubusercontent.com/117457616/208311466-261d255f-3bbf-4615-8b1c-9fe7e4eb707c.png)

-ใช้คำสั่ง

    sudo apt install qemu-guest-agent
    sudo systemctl start qemu-guest-agent
    
-ใช้คำสั่งนี้เพื่อตรวจสอบสถานะการทำงานของ QEMU Guest Agent

    sudo systemctl status qemu-guest-agent

![image](https://user-images.githubusercontent.com/117457616/208311554-ee9804c4-7d8c-40a1-bba6-abb35a753d7e.png)

-หน้า Summary จะมีเลข IPs เพิ่มมาหลังจากทำการเปิดใช้ QEMU Guest Agent

![image](https://user-images.githubusercontent.com/117457616/208311615-798bd848-c7b6-489a-8405-4c645501ded2.png)

-ปิดเครื่อง และกด More เลือก Convert to template

![image](https://user-images.githubusercontent.com/117457616/208311643-f1c35afa-2531-40d3-a7a0-8972570ca742.png)

-clone from template สร้าง vm ใหม่จำนวน 2 vm

![image](https://user-images.githubusercontent.com/117457616/208311770-d31642d9-7df5-48b0-97f8-4067c030b34c.png)

-change hostname สำหรับ vm ใหม่

    sudo hostnamectl hostname *ชื่ออะไรก็ได้*
    
-กดเลือกเครื่อง clone แล้วเปลี่ยน IP โดยใช้คำสั่ง

    sudo -i
    rm /var/lib/dbus/machine-id
    nano /etc/machine-id 
    ln -s /etc/machine-id /var/lib/dbus/machine-id
    
-Restart os

-เครื่อง Clone 1

![image](https://user-images.githubusercontent.com/117457616/208311830-167864b9-6569-4282-bed0-74905754e7cf.png)

![image](https://user-images.githubusercontent.com/117457616/208311838-78a254f2-ecd0-424f-a8b6-8455a31aa750.png)

-เครื่อง Clone 2

![image](https://user-images.githubusercontent.com/117457616/208311845-e12b4fc9-b87e-473e-a3fd-df0da3d22e90.png)

![image](https://user-images.githubusercontent.com/117457616/208311848-c0148666-bffe-41ff-b1cb-faac004ac560.png)

# create vm from other os

-สร้าง Create VM ตั้งค่าต่างๆตามที่กำหนด โดยจะใช้ระบบปฏิบัติการ kali-linux-2022-3-live-amd64 
-ตั้งชื่อ VM ตัวอักษรชื่อภาษาอังกฤษตัวเองอย่างน้อย 3 ตัว-otherOS-เลข VM ID

![image](https://user-images.githubusercontent.com/117457616/208313443-cc1dc1d7-f258-4ab9-85f0-55aa0fbb1a24.png)
![image](https://user-images.githubusercontent.com/117457616/208313457-93c28cdf-fd0c-4a8e-b7e1-fe65e812721c.png)

# create create container template

-กดเลือกปุ่ม Create CT

-Create LXC Container หน้า General ใส่รายละเอียดข้อมูล แล้ว next เลือกค่า default

![image](https://user-images.githubusercontent.com/117457616/208313501-debddd93-4b59-47a7-a4b8-111b2fded833.png)

-Create LXC Container หน้า Network เลือก IPv4 เป็น DHCP และ IPv6 เป็น SLAAC

![image](https://user-images.githubusercontent.com/117457616/208313516-a4a8f020-43f4-4675-af8a-695caf873bce.png)

-หน้า Summary

![image](https://user-images.githubusercontent.com/117457616/208313572-61e7df8f-d084-4cab-bc3d-303209f738e8.png)

-หน้า console

![image](https://user-images.githubusercontent.com/117457616/208313593-ba1b4234-88f9-4c5d-8eeb-7a02ff4a127c.png)












