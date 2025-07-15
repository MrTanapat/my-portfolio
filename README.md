## Part 1: Git Fundamentals & Local Development - [งานเดี่ยว] (40 คะแนน)

### วัตถุประสงค์
- เรียนรู้การใช้งาน Git commands พื้นฐาน
- สามารถเชื่อมต่อ Local Repository กับ GitHub
- ฝึกการทำงานกับ branching และ merging

### เตรียมตัวก่อนเริ่มทำแลป
1. ติดตั้ง Git บนเครื่องคอมพิวเตอร์
2. สร้างบัญชี GitHub
3. ตั้งค่า Git configuration

```bash
# ตั้งค่าชื่อและอีเมล
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# ตรวจสอบการตั้งค่า
git config --list
```
Result
<p align="center">
  <img width="578" height="36" alt="Screenshot 2025-07-15 190936" src="https://github.com/user-attachments/assets/6ba2b1d2-9cc9-4682-a8f1-d32c63928d7c" />
</p>

### ขั้นตอนที่ 1: สร้าง Repository และเชื่อมต่อกับ GitHub
 
#### 1.1 สร้างโฟลเดอร์โปรเจกต์
```bash
# สร้างโฟลเดอร์โปรเจกต์
mkdir my-portfolio
cd my-portfolio

# เริ่มต้น Git repository
git init
```
Result
<p align="center">
  <img width="274" height="30" alt="Screenshot 2025-07-15 191610" src="https://github.com/user-attachments/assets/63e72407-cbf7-4726-91ad-a04585e97e2c" /> <br>
  <img width="615" height="54" alt="Screenshot 2025-07-15 191759" src="https://github.com/user-attachments/assets/24f59225-3bbc-46ef-9b3f-14e1e4bea65c" />
</p>

#### 1.2 สร้างไฟล์พื้นฐาน
Result
<p align="center">
  <img width="273" height="83" alt="Screenshot 2025-07-15 192237" src="https://github.com/user-attachments/assets/e4d3ff10-1f3d-48d4-81d2-d65f4938a193" />
</p>

สร้างไฟล์ `index.html`:
```html
<!DOCTYPE html>
<html lang="th">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>สวัสดี! ฉันคือ [ชื่อของคุณ]</h1>
        <p>นักพัฒนาเว็บไซต์มือใหม่</p>
    </header>
    
    <main>
        <section id="about">
            <h2>เกี่ยวกับฉัน</h2>
            <p>ฉันกำลังเรียนรู้การพัฒนาเว็บไซต์และตื่นเต้นมากกับเทคโนโลยีใหม่ๆ</p>
        </section>
        
        <section id="skills">
            <h2>ทักษะ</h2>
            <ul>
                <li>HTML</li>
                <li>CSS</li>
                <li>JavaScript (เรียนรู้อยู่)</li>
            </ul>
        </section>
    </main>
    
    <footer>
        <p>&copy; 2025 My Portfolio</p>
    </footer>
</body>
</html>
```

สร้างไฟล์ `style.css`:
```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
    color: #333;
    background-color: #f4f4f4;
}

header {
    background-color: #2c3e50;
    color: white;
    text-align: center;
    padding: 2rem;
}

header h1 {
    margin-bottom: 0.5rem;
}

main {
    max-width: 800px;
    margin: 2rem auto;
    padding: 0 1rem;
}

section {
    background-color: white;
    margin-bottom: 2rem;
    padding: 2rem;
    border-radius: 8px;
    box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}

section h2 {
    color: #2c3e50;
    margin-bottom: 1rem;
}

ul {
    list-style-type: none;
    padding-left: 0;
}

ul li {
    background-color: #3498db;
    color: white;
    padding: 0.5rem 1rem;
    margin-bottom: 0.5rem;
    border-radius: 4px;
}

footer {
    background-color: #2c3e50;
    color: white;
    text-align: center;
    padding: 1rem;
    margin-top: 2rem;
}
```

#### 1.3 เพิ่มไฟล์ไปยัง Repository
```bash
# ตรวจสอบสถานะไฟล์
git status

# เพิ่มไฟล์ทั้งหมดไปยัง staging area
git add .

# ตรวจสอบสถานะอีกครั้ง
git status

# Commit ครั้งแรก
git commit -m "Initial commit: Add basic portfolio structure"
```
Result
<p align="center">
  <img width="637" height="432" alt="Screenshot 2025-07-15 192428" src="https://github.com/user-attachments/assets/45fa805c-43e8-4957-8456-f586a915e504" />
</p>

#### 1.4 สร้าง Repository บน GitHub และเชื่อมต่อ
1. ไปที่ GitHub.com และล็อกอิน
2. คลิก "New Repository"
3. ตั้งชื่อ repository เป็น "my-portfolio"
4. ไม่ต้องเลือก "Initialize with README"
5. คลิก "Create Repository"

```bash
# เชื่อมต่อกับ GitHub repository
git remote add origin git@github.com:[your-username]/my-portfolio.git

# ตรวจสอบการเชื่อมต่อ
git remote -v

# Push ไฟล์ไปยัง GitHub
git push -u origin main
```
Result
<p align="center">
  <img width="435" height="48" alt="Screenshot 2025-07-15 192951" src="https://github.com/user-attachments/assets/4904c0e1-fe7d-414f-9967-3e1fb6f7df58" />
  <img width="540" height="175" alt="Screenshot 2025-07-15 194209" src="https://github.com/user-attachments/assets/b1a793ae-f744-44f9-9657-ad466fffc69f" />
</p>

### ขั้นตอนที่ 2: การทำงานกับ Branches

#### 2.1 สร้าง Branch ใหม่สำหรับเพิ่มฟีเจอร์
```bash
# สร้าง branch ใหม่และเปลี่ยนไป
git checkout -b feature/add-projects

# ตรวจสอบ branch ปัจจุบัน
git branch
```
Result
<p align="center">
  <img width="481" height="81" alt="Screenshot 2025-07-15 194434" src="https://github.com/user-attachments/assets/52c3495a-9772-4bf0-9fa9-b385787cecaf" />
</p>

#### 2.2 เพิ่มเนื้อหาใน Branch ใหม่
แก้ไขไฟล์ `index.html` โดยเพิ่มส่วน projects หลัง section skills:
```html
        <section id="projects">
            <h2>โปรเจกต์ของฉัน</h2>
            <div class="project">
                <h3>เว็บไซต์ Portfolio</h3>
                <p>เว็บไซต์แสดงผลงานส่วนตัวที่สร้างด้วย HTML, CSS</p>
                <a href="#" class="project-link">ดูโปรเจกต์</a>
            </div>
            <div class="project">
                <h3>To-Do List App</h3>
                <p>แอปพลิเคชันจดบันทึกรายการสิ่งที่ต้องทำ (กำลังพัฒนา)</p>
                <a href="#" class="project-link">ดูโปรเจกต์</a>
            </div>
        </section>
```
Result
<p align="center">
  <img width="785" height="298" alt="Screenshot 2025-07-15 194733" src="https://github.com/user-attachments/assets/a353082a-07ec-4efe-b4c7-a3760de19022" />
</p>

เพิ่ม CSS สำหรับ projects ในไฟล์ `style.css`:
```css
.project {
    border: 1px solid #ddd;
    padding: 1.5rem;
    margin-bottom: 1rem;
    border-radius: 4px;
    background-color: #f9f9f9;
}

.project h3 {
    color: #2c3e50;
    margin-bottom: 0.5rem;
}

.project-link {
    display: inline-block;
    background-color: #3498db;
    color: white;
    padding: 0.5rem 1rem;
    text-decoration: none;
    border-radius: 4px;
    margin-top: 1rem;
}

.project-link:hover {
    background-color: #2980b9;
}
```
Result
<p align="center">
  <img width="774" height="500" alt="Screenshot 2025-07-15 194820" src="https://github.com/user-attachments/assets/b73beb4d-6d19-4046-b617-9197834eb202" />
</p>

#### 2.3 Commit การเปลี่ยนแปลง
```bash
# ตรวจสอบการเปลี่ยนแปลง
git diff

# เพิ่มไฟล์ที่แก้ไข
git add .

# Commit
git commit -m "Add projects section with styling"

# Push branch ใหม่ไปยัง GitHub
git push -u origin feature/add-projects
```
Result
<p align="center">
  <img width="635" height="486" alt="Screenshot 2025-07-15 195030" src="https://github.com/user-attachments/assets/ff74e1b0-4f29-48cc-af08-25d9dfdcf37f" />
  <img width="684" height="308" alt="Screenshot 2025-07-15 195140" src="https://github.com/user-attachments/assets/7954a3e2-c4ec-4a8c-9c1f-f88e86430713" />
</p>

### ขั้นตอนที่ 3: Merging และ Pull Request

#### 3.1 สร้าง Pull Request บน GitHub
1. ไปที่ repository บน GitHub
2. คลิก "Compare & pull request"
3. เขียนรายละเอียดการเปลี่ยนแปลง
4. คลิก "Create pull request"

Result
<p align="center">
  <img width="917" height="67" alt="Screenshot 2025-07-15 195523" src="https://github.com/user-attachments/assets/c3def985-eb0b-4754-8061-f6231b923d06" />
  <img width="822" height="846" alt="Screenshot 2025-07-15 195934" src="https://github.com/user-attachments/assets/4aed52df-92e2-429d-8a9e-732bd49f73e0" />
</p>

#### 3.2 Merge กลับไปยัง Main Branch
```bash
# เปลี่ยนกลับไปยัง main branch
git checkout main

# Pull การเปลี่ยนแปลงล่าสุดจาก GitHub
git pull origin main

# Merge feature branch
git merge feature/add-projects

# Push การเปลี่ยนแปลงไปยัง GitHub
git push origin main

# ลบ branch ที่ไม่ใช้แล้ว
git branch -d feature/add-projects
```
Result
<p align="center">
  <img width="501" height="68" alt="Screenshot 2025-07-15 200256" src="https://github.com/user-attachments/assets/cb1b4f69-cec1-4691-a8f5-3c2a80b8ace3" />
</p>

### ขั้นตอนที่ 4: การจัดการ Conflicts

#### 4.1 สร้าง Conflict เพื่อฝึกแก้ไข
```bash
# สร้าง branch ใหม่
git checkout -b feature/update-contact

# แก้ไข footer ในไฟล์ index.html
# เปลี่ยนจาก: <p>&copy; 2025 My Portfolio</p>
# เป็น: <p>&copy; 2025 My Portfolio | Contact: myemail@example.com</p>

git add .
git commit -m "Add contact info to footer"
git push -u origin feature/update-contact
```
Result
<p align="center">
  <img width="697" height="306" alt="Screenshot 2025-07-15 200655" src="https://github.com/user-attachments/assets/43353b0b-63ea-4c7d-9d53-091970343c57" />
</p>

#### 4.2 สร้างการเปลี่ยนแปลงใน Main Branch
```bash
# กลับไปยัง main
git checkout main

# แก้ไข footer เหมือนกัน แต่ต่างกัน
# เปลี่ยนเป็น: <p>&copy; 2025 My Portfolio | Version 1.0</p>

git add .
git commit -m "Add version info to footer"
git push origin main
```

#### 4.3 แก้ไข Conflict
```bash
# เปลี่ยนกลับไปยัง feature branch
git checkout feature/update-contact

# พยายาม merge main เพื่อสร้าง conflict
git merge main

# แก้ไข conflict ในไฟล์
# เลือกรวม: <p>&copy; 2025 My Portfolio | Version 1.0 | Contact: myemail@example.com</p>

git add .
git commit -m "Resolve merge conflict in footer"
git push origin feature/update-contact
```
Result
<p align="center">
  <img width="500" height="200" alt="Screenshot 2025-07-15 201307" src="https://github.com/user-attachments/assets/5e466306-79b1-43f6-bf57-9a9bf5e6636d" />
</p>

### งานที่ต้องส่ง Part 1
1. ลิงก์ GitHub Repository
2. Screenshot ของ commit history
3. Screenshot ของ Pull Request ที่สร้าง
4. ไฟล์ index.html และ style.css ที่สมบูรณ์

---

## 📚 Additional Resources

- [Git Official Documentation](https://git-scm.com/doc)
- [GitHub Desktop Documentation](https://docs.github.com/en/desktop)
- [VS Code Git Integration](https://code.visualstudio.com/docs/editor/versioncontrol)
- [Interactive Git Tutorial](https://learngitbranching.js.org/)

## Resources & References

### Git Commands Reference
```bash
# พื้นฐาน
git init
git clone <url>
git add <file>
git commit -m "message"
git push
git pull

# Branching
git branch
git checkout -b <branch>
git merge <branch>
git branch -d <branch>

# Remote
git remote add origin <url>
git remote -v
git push -u origin <branch>

# Advanced
git rebase
git cherry-pick
git stash
git tag
```

## Rubric การให้คะแนน

### Part 1: Git Fundamentals (40 คะแนน)

| หัวข้อ | ดีเยี่ยม (9-10) | ดี (7-8) | ปานกลาง (5-6) | ต้องปรับปรุง (1-4) |
|--------|----------------|----------|----------------|-------------------|
| **Repository Setup** (10 คะแนน) | Repository ตั้งค่าถูกต้อง มี commit history ที่ดี | Repository ตั้งค่าถูกต้อง มี commit เพียงพอ | Repository ตั้งค่าได้ แต่ commit ไม่เพียงพอ | Repository ไม่สมบูรณ์ |
| **Branch Management** (10 คะแนน) | ใช้ branch ถูกต้อง merge สำเร็จ | ใช้ branch ได้ แต่ merge มีปัญหาเล็กน้อย | สร้าง branch ได้ แต่ merge ไม่สมบูรณ์ | ไม่สามารถใช้ branch ได้ |
| **Code Quality** (10 คะแนน) | Code สะอาด ทำงานได้สมบูรณ์ | Code ทำงานได้ มีข้อผิดพลาดเล็กน้อย | Code ทำงานได้บางส่วน | Code ไม่ทำงาน |
| **Git Commands** (10 คะแนน) | ใช้ commands ได้หลากหลาย และถูกต้อง | ใช้ commands พื้นฐานได้ดี | ใช้ commands ได้บางส่วน | ใช้ commands ไม่ถูกต้อง |

**Next**: Continue to [Part 2: Advanced Git Workflow & Team Collaboration](../part2)
