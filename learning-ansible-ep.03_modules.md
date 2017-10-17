# Ansible พื้นฐานที่ (ตัวเอง) ควรรู้ Ep.03 - Modules  

![Ansible Logo](https://upload.wikimedia.org/wikipedia/fr/thumb/4/4b/Ansible_logo.png/480px-Ansible_logo.png "Ansible Logo")

ใน Ep. ก่อนหน้านั้นเราได้รู้จักกับ [Ansible](https://gist.github.com/maprangzth/6086d9a80704707f309e5cffbbd9af1d "What's Ansible?") และ [Inventory](https://gist.github.com/maprangzth/ab307de46f063740c0720252660dfdeb "Ansible Inventory") กันไปเป็นที่เรียบร้อยแล้ว แต่แค่นั้นเรายังไม่สามารถใช้งาน Ansible ได้นะครัชชช สิ่งที่ Ansible ต้องการอีกตัวนึง คือ **Modules**  

## Modules คืออะไร?  
Module คือ ชุดคำสั่งที่ (สามารถ Execute ได้) เขียนขึ้นมาเพื่อให้ทำงานตามที่เราต้องการ ซึ่ง Ansible นั้นมี Module ที่ถูกเขียนไว้แล้วเยอะแยะมากมาย เราสามารถเรียกใช้ได้เลย (รายชื่อ modules และวิธีใช้งานดูได้จาก [ที่นี่](http://docs.ansible.com/ansible/latest/modules.html)) หรือถ้าใครอยากเขียนขึ้นมาใช้เองในองค์กรก็สามารถทำได้เหมือนกัน โดยมีข้อแม้ว่าตัวภาษาที่ใช้เขียนต้องรีเทิร์น Output เป็น JSON ได้ แต่ส่วนมากแล้วเขาใช้ Python ถ้าสนใจตามไปอ่านเพิ่มเติม [ที่นี่](http://docs.ansible.com/ansible/latest/dev_guide/developing_modules.html)  

## การทำงานของ Modules
ถ้าใครเข้าไปอ่านใน Doc. เขาก็จะบอกว่ามันทำงานแบบ "idempotent" อธิบายให้เข้าใจง่ายๆ คือ Module เนี่ยจะทำงานเฉพาะสิ่งที่อยู่ไม่ได้อยู่ใน desired state เท่านั้น (ไม่อยู่ใน state ที่ต้องการ) และต่อให้เราสั่ง Ansible สักกี่รอบมันก็จะได้ผลลัพธ์เหมือนเดิมทุกรอบ เช่น สั่งให้ Ansible ทำการติดตั้ง package nginx ถ้าหาก nginx ถูกติดตั้งอยู่แล้วมันก็จะไม่ทำงานให้ แต่ถ้ายังไม่ถูกติดตั้ง มันก็จะทำการติดตั้งให้ และใครที่คิดจะเขียน Module ขึ้นมาใช้งานก็**ควร**จะยึดหลักนี้ด้วยน๊ะจ๊ะ จะได้ไม่เป็นภาระของคนที่ใช้งาน

## Modules พื้นฐานที่ใช้งานบ่อยๆ  
* [ping](http://docs.ansible.com/ansible/latest/ping_module.html)
* [yum](http://docs.ansible.com/ansible/latest/yum_module.html)
* [apt](http://docs.ansible.com/ansible/latest/apt_module.html)
* [service](http://docs.ansible.com/ansible/latest/service_module.html)
* [file](http://docs.ansible.com/ansible/latest/file_module.html)
* [lineinfile](http://docs.ansible.com/ansible/latest/lineinfile_module.html)  
* [copy](http://docs.ansible.com/ansible/latest/copy_module.html)  
* [shell](http://docs.ansible.com/ansible/latest/shell_module.html)  
* [command](http://docs.ansible.com/ansible/latest/command_module.html)
* [template](http://docs.ansible.com/ansible/latest/template_module.html)
* [user](http://docs.ansible.com/ansible/latest/user_module.html)
* [apt_repository](http://docs.ansible.com/ansible/latest/apt_repository_module.html)
* [yum_repository](http://docs.ansible.com/ansible/latest/yum_repository_module.html)
* [selinux](http://docs.ansible.com/ansible/latest/selinux_module.html)  

**การทำงานของแต่ละ Modules นั้น Official Document เขาเขียนอธิบายไว้ชัดเจน แจ่มแจ้งอยู่แล้วฉะนั้นตามไปเสพกันได้เลย ^^**

## สรุป  
Ansible นั้นมี Modules ให้ใช้งานเยอะมาก (หลักร้อย) ถือว่าพกพาความสะดวกสบายมาให้ผู้ใช้งานอย่างมาก แต่สำหรับมือใหม่หัดขับที่หลงเข้าในดง Ansible ก็มีใช้อยู่ไม่กี่อันหรอก ตาม List ด้านบนนั่นแหละครับ (อาจจะดูน้อยแต่ถ้าลอง Search หรือหาอ่าน Tutorial ที่อื่นๆ ก็ใช้เหมือนผมนี่แหละ 555) สุดท้ายฝากทุกท่านที่หลงเข้ามาอ่านไปศึกษาวิธีใช้งานของแต่ละ Module เพิ่มด้วยนะครับ จะให้ดีก็ศึกษา Modules อื่นๆที่ไม่ได้กล่าวมาด้วยเด้อ ลองใช้บ่อยๆ รันบ่อยๆ เดี๋ยวคล่องเอง เชื่อหมอ... หมอเรียนมา!!! 
