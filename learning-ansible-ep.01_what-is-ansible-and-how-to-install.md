# Ansible พื้นฐานที่ (ตัวเอง) ควรรู้ - Ep.01  

## เกริ่นนำกันซักหน่อย  
ที่มาที่ไปก็คือ เสาร์-อาทิตย์ ว่างจัด จริงๆ ก็พยายามทำให้ตัวเองไม่ว่างนั่นแหละ คือนั่งอ่านหนังสือหรืออ่านบทความที่คนอื่นเขาเขียน แต่ก็อย่างว่าแค่นั่งอ่าน 555+ อ่านจบแล้วทำไรล่ะ เบื่อ...นั่งแดรกกเบียร์แม่มมม (กิจกรรมหลักของผมเลยก็ว่าได้) แต่ไม่กี่วันที่ผ่านมารัฐบาลเสือกขึ้นภาษีอีก ร้องเฮ้ดังมากกกก จะให้ทำแบบเมื่อก่อนคงไม่ได้ ก็เลยสะพายเป้ใส่โน๊ตบุคไปนั่งร้านกาแฟสั่งชาเขียวเย็นๆ อ่านหนังสือชิวๆ แอร์ก็พร้อม สาวๆ ก็มีให้มองคงไม่มีอะไรดีไปกว่านี้อีกแล้วววว บวกกับเราเองก็สนใจตัว **Ansible** ด้วยอยู่แล้ว และที่สำคัญ **Infrastructure as Code** เป็นสิ่งที่ควรค่าแก่การศึกษา เพราะ System Admin Thailand 4.0 เขาไม่มานั่ง Setup Infrastructure แบบวิถีดั้งเดิมกันแล้ว ปั๊ดโถ๊ว!!! (เสียงและสีหน้าลุงตู่ตอนตอบคำถามนักข่าว)  

## Ansible คืออะไร?  
```
Ansible is a radically simple IT automation engine that automates cloud provisioning, configuration management, application deployment, intra-service orchestration, and many other IT needs.

```
จาก Official documents บอกชัดเจนอยู่แล้วคงไม่ต้องอธิบายเยอะ แต่ขอสรุปง่ายๆ สั้นๆ ดังนี้  

```
Ansible คือ agent-less IT automation tool ทำงานผ่าน SSH Protocol (สำหรับ Mac และ UNIX-like system) และ winrm (Windows) โดยที่เราไม่ต้องไปติดตั้ง agent ให้วุ่นวาย!!!  
```  

แล้ว Ansible มันทำอะไรได้บ้างล่ะ? (Copy ข้อความด้านบนมาแปะอีกทีนึง)  

* cloud provisioning  
* configuration management  
* application deployment  
* intra-service orchestration  
* อันสุดท้าย อยากเอาไปทำอะไร ก็แล้วแต่ใจเธอต้องการ (เพราะ Ansible มี Modules ให้ใช้เยอะมาก)  

## ท่าที่ใช้ในการติดตั้ง Ansible   
ในการติดตั้ง Ansible มีหลายท่าให้เลือก เช่น  
* ท่ามาตรฐาน - ติดตั้งผ่าน Package Manager ของแต่ล่ะ OS (**yum**, **dnf** และ **apt** เป็นต้น)
* ท่าเดียวครอบคลุมจักรวาล - ติดตั้งผ่าน Python's package management tool (**pip**)  
* ท่ายาก - ติดตั้งจาก Source Code (โหดสัส รัสเซีย)  

แต่สำหรับผมใช้ท่ามาตรฐานก็พอครับ มาเริ่มกันเลย  
 
### CentOS และ Redhat:  
```
$ yum install ansible
```  

`*** RHEL Base ต้องติดตั้ง EPEL Repo. ก่อนนะครัชชชชช`  

### Fedora:  
```
$ dnf install ansible
```  

### Ubuntu และ Debian:  
```
$ apt-get install ansible
```  

###  ติดตั้งผ่าน **pip**:  
```
$ sudo easy_install pip
$ sudo pip install ansible
```  

ส่วนวิธีติดตั้งนอกเหนือจาก Package Manager และ OS อื่นๆ ตามไปอ่านกัน [ที่นี่](http://docs.ansible.com/ansible/latest/intro_installation.html) ครับ  

เอาล่ะ หลังจากตั้งแล้วก็ตรวจสอบความเรียบร้อยกันหน่อย  

ปล. ส่วนตัวผมใช้ [Fedora 26](https://fedoraproject.org/) นะครับ ;)  

```
$ ansible --version
ansible 2.3.2.0
  config file = /etc/ansible/ansible.cfg
  configured module search path = Default w/o overrides
  python version = 2.7.13 (default, Sep  5 2017, 08:53:59) [GCC 7.1.1 20170622 (Red Hat 7.1.1-3)]
```  

ถ้าได้ผลลัพธ์(คล้ายๆ) แบบนี้ก็แสดงว่า Ansible เราพร้อมใช้งานแล้วครับ  

## สรุป Ep.01 ได้อะไรบ้าง?  
Ep.01 ได้ทำความรู้จักว่า Ansible คืออะไร? ทำอะไรได้บ้าง? และติดตั้งยังไง? Ep.02 จะพาไปรู้จักกับ **Inventory** และพาไหว้ครูด้วยคำสั่งพื้นฐานแบบ **Ad-Hoc Command** กันครับ (อารมณ์ประมาณว่าเราเรียน Computer Programming หลังจากติดตั้งก็ต้อง "Hello, world.")  
