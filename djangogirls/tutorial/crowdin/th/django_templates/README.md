# Django templates

ได้เวลาแสดงข้อมูลกันบ้างแล้ว! Django นั้นให้เครื่องมือที่ทำงานนี้ได้อย่างสะดวก นั้นคือ **template tags**

## แล้วอะไรคือ template tags?

ใน HTML นั้น คุณไม่สามารถเขียนโค้ด Python ลงไปได้ เพราะเบราว์เซอร์ไม่สามารถเข้าใจได้ พวกมันเข้าใจเฉพาะ HTML เรารู้ว่า HTML นั้นข้อมูลจะคงที่คงตัว ขณะที่ Python นั้นตรงกันข้ามกันเลย

**Django template tags** นั้นทำให้เราสามารถใช้โค้ดที่เหมือนกับ Python ให้เป็น HTML, ดังนั้นคุณสามารถสร้างหน้าเว็บแบบไม่คงที่ได้อย่างรวดเร็วและง่ายขึ้น เย้ย!

## แสดง template รายการโพสต์

ในบทที่แล้ว เราส่งรายการของโพสต์จากในตัวแปร `posts` ไปยัง template และตอนนี้เราจะแสดงรายการโพสต์ออกมาในรูปแบบ HTML

การจะแสดงผลค่าตัวแปรใน Django template เราจะใช้วงเล็บก้ามปูสองอัน ที่มีชื่อตัวแปรอยู่ข้างใน แบบนี้:

    html
    {{ posts }}
    

ลองแก้ไขไฟล์ template `blog/templates/blog/post_list.html` แทนที่ทุกอย่างจาก `<div>` ที่สอง ไปจนถึง `</div>` ที่สาม โดยแทนที่ด้วย `{{ posts }}` บันทึกไฟล์และโหลดหน้าเว็บอีกครั้งเพื่อดูผลลัพธ์:

![รูปที่ 13.1][1]

 [1]: images/step1.png

อย่างที่คุณเห็น เราได้ผลลัพธ์แบบนี้:

    [<Post: My second post>, <Post: My first post>]
    

ตรงนี้หมายความว่า Django สามารถเข้าใจและรู้ว่านี่คือรายการวัตถุ ยังจำวิธีที่เราแสดงรายการจากในบท **แนะนำให้รู้จัก Python** ได้ไหม? ใช่แล้ว ใช้การวนลูปไง! ใน Django template เราสามารถทำแบบนี้ได้:

    html
    {% for post in posts %}
        {{ post }}
    {% endfor %}
    

ลองแบบนี้ใน template ของคุณ

![รูปที่ 13.2][2]

 [2]: images/step2.png

มันทำงานถูกต้อง! แต่เราต้องการให้มันแสดงผลเหมือนกับโพสต์แบบคงที่ เหมือนอย่างที่เราเคยสร้างไว้ในบท **แนะนำให้รู้จัก HTML** คุณสามารถผสมผสานการใช้ HTML กับ template tag ในส่วน `body` จะมีหน้าตาแบบนี้:

    html
    <div>
        <h1><a href="/">Django Girls Blog</a></h1>
    </div>
    
    {% for post in posts %}
        <div>
            <p>published: {{ post.published_date }}</p>
            <h1><a href="">{{ post.title }}</a></h1>
            <p>{{ post.text|linebreaks }}</p>
        </div>
    {% endfor %}
    

{% raw %}ทุกสิ่งที่คุณใส่ไประหว่าง `{% for %}` และ `{% endfor %}` จะถูกทำซ้ำหลายรอบตามจำนวนวัตถุในรายการ โหลดหน้าเว็บอีกครั้ง:{% endraw %}

![รูปที่ 13.3][3]

 [3]: images/step3.png

คุณคงสงสัย ว่าเราใช้โค้ดหน้าตาต่างกันเล็กน้อย คือ `{{ post.title }}` และ `{{ post.text }}`? เราเข้าถึงแต่ละข้อมูลที่ได้สร้างไว้ในโมเดล `Post` ของเรา ในส่วนของ `|linebreaks` คือการแปลงให้ข้อความของโพสต์ที่เป็นการขึ้นบรรทัดใหม่ ให้เป็นย่อหน้า

## ส่วนสุดท้าย

ตอนนี้เราน่าจะลองเอาเว็บของเราขึ้นบนอินเทอร์เน็ตแล้วนะ? ลองเอาขึ้น PythonAnywhere อีกครั้ง นี่คือขั้นตอนที่เราเคยทำ...

*   อันดับแรก นำไฟล์ขึ้นไปที่ Github

    $ git status
    [...]
    $ git add -A .
    $ git status
    [...]
    $ git commit -m "Modified templates to display posts from database."
    [...]
    $ git push
    

*   จากนั้นไปที่ [PythonAnywhere][4] และไปยังส่วน **Bash console** (หรือเปิดอันใหม่) และรันคำสั่ง:

 [4]: https://www.pythonanywhere.com/consoles/

    $ cd my-first-blog
    $ git pull
    [...]
    

*   สุดท้าย ไปยัง [Web tab][5] และกดปุ่ม **Reload** บนเว็บของคุณ การแก้ไขของคุณจะปรากฎเป็นล่าสุดแล้ว!

 [5]: https://www.pythonanywhere.com/web_app_setup/

ยินดีด้วย! ตอนนี้ลองเพิ่มโพสต์ใหม่ที่หน้า Django admin(อย่าลืมส่วน published_date!) โหลดหน้าเว็บใหม่อีกครั้ง ดูว่ามีอะไรเพิ่มไหม

ทำงานถูกต้องใช่ไหม? เราภูมิใจในตัวคุณ! เอาล่ะพักสายตาจากหน้าคอมพิวเตอร์สักนิดหน่อยกัน :)

![รูปที่ 13.4][6]

 [6]: images/donut.png