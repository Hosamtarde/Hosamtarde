<!-- ===================== HEADER ===================== -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=190&section=header&text=Hosam%20Tarade&fontSize=46&fontColor=ffffff&animation=fadeIn&fontAlignY=36&desc=Backend%20Developer%20%E2%80%A2%20NestJS%20%E2%80%A2%20TypeScript%20%E2%80%A2%20PostgreSQL&descAlignY=58&descSize=17" />
</p>

<p align="center">
  <a href="https://hosamtarade.com">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=19&pause=1200&color=38BDF8&center=true&vCenter=true&width=650&lines=I+build+the+part+nobody+sees+%E2%80%94+APIs%2C+data+models%2C+auth;Two+buyers%2C+one+unit+left%2C+one+winner+%E2%9A%A1;Transactions+%26+constraints+%3E+clever+code;Backend+Intern+%40+Wahj+%E2%80%94+open+to+work" alt="Typing SVG" />
  </a>
</p>

<p align="center">
  <a href="https://hosamtarade.com"><img src="https://img.shields.io/badge/Portfolio-hosamtarade.com-38BDF8?style=for-the-badge&logo=googlechrome&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/hosamtarade"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="mailto:tardehosam@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
  <a href="https://drive.google.com/file/d/15l-bx26RzTAuw7uODagYdNGhM2I2RNa5/view?usp=drivesdk"><img src="https://img.shields.io/badge/CV-111827?style=for-the-badge&logo=readthedocs&logoColor=white" /></a>
</p>

<p align="center">
  <img src="https://komarev.com/ghpvc/?username=Hosamtarde&style=flat-square&color=38BDF8&label=Profile+Views" />
</p>

---

## 👨‍💻 About Me

```ts
const hosam = {
  role:        "Backend Developer Intern @ Wahj",
  location:    "Hebron, Palestine 🇵🇸",
  education:   "BSc Computer Science — Palestine Polytechnic University",
  focus:       ["REST APIs", "Data Modeling", "Auth & RBAC", "Concurrency-safe systems"],
  principles:  ["Clean Architecture", "SOLID", "Versioned migrations", "Validated input"],
  currently:   "Building 3 NestJS systems",
  openToWork:  true,
};
```

I spend more time in the **schema** than the style sheet. I started with PHP & MySQL on a course registration system that had to stay honest under concurrent edits — that taught me why **transactions and constraints matter more than clever code**. Today I work with **NestJS & TypeScript**, building systems with role guards, rotating refresh tokens, versioned migrations, and live Swagger docs.

---

## 💼 Experience

**🟢 Backend Developer Intern — Wahj** · Hebron, on-site · *Jul 2026 – Present*
Building and maintaining REST APIs with NestJS & TypeScript, modeling data in PostgreSQL with Prisma ORM, implementing authentication & authorization, and shipping through Git code reviews with Clean Architecture.

**Software Development Trainee — Gaza Sky Geeks (Skill Stack Path)** · remote · *Feb – Aug 2025*
Python, data structures, algorithms, OOP, and peer review across a distributed cohort.

**Game Development Trainee — Google DSC, Zarqa University** · remote · *Jul – Aug 2025*
Game programming fundamentals with C# and Unity.

---

## 🧰 Tech Stack

**Languages**
<p align="left">
  <img src="https://skillicons.dev/icons?i=ts,js,php,py,cs,cpp&perline=8" />
</p>

**Backend & Data**
<p align="left">
  <img src="https://skillicons.dev/icons?i=nestjs,nodejs,postgres,mysql,prisma&perline=8" />
  <br/>
  <img src="https://img.shields.io/badge/TypeORM-FE0803?style=flat-square&logo=typeorm&logoColor=white" />
  <img src="https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white" />
  <img src="https://img.shields.io/badge/Swagger-85EA2D?style=flat-square&logo=swagger&logoColor=black" />
  <img src="https://img.shields.io/badge/RBAC-4B5563?style=flat-square" />
  <img src="https://img.shields.io/badge/Laravel%20Sanctum-FF2D20?style=flat-square&logo=laravel&logoColor=white" />
</p>

**Tools**
<p align="left">
  <img src="https://skillicons.dev/icons?i=docker,git,github,postman,nextjs,react,unity&perline=8" />
</p>

---

## 🚀 Featured Projects

### 📦 [Multi-Branch Inventory System](https://github.com/Hosamtarde/Distributed-Multi-Branch-Inventory-Management-System)
Backend for a retail chain where every branch holds its own stock and one online store sells across all of them. Stock changes run inside a transaction with a **pessimistic write lock** — proven by a script firing two identical requests via `Promise.all`: exactly one succeeds. **0 oversells.**

`NestJS` `TypeScript` `PostgreSQL` `TypeORM` `JWT` `RBAC` `Docker` `Swagger`

<details>
<summary>⚡ See the concurrency-safe core</summary>

```ts
// two buyers, one unit left, one winner
return this.dataSource.transaction(async (m) => {
  const record = await m.findOne(Inventory, {
    where: { id },
    lock: { mode: 'pessimistic_write' },
  });

  if (record.quantity + change < 0)
    throw new BadRequestException('Insufficient stock in this branch');

  record.quantity += change;
  return m.save(record);
});
```
</details>

### 🧑‍💼 Human Resource Management System — *Graduation Project*
HR platform for SMEs covering the full employee lifecycle: applications, attendance, leave & loan requests, tasks, performance reviews, and payroll. Four inherited roles (Applicant → Employee → Manager → HR Admin), throttled login, and guarded endpoints. I own the backend: schema, migrations, auth, and approval flows.

`NestJS` `TypeScript` `MySQL` `TypeORM` `JWT` `RBAC` `Docker` `Swagger` · 🔒 *Private repo — available on request*

### 💼 [Job & Internship Platform](https://github.com/Hosamtarde/job-platform)
Companies post roles, candidates apply and track status through a fixed lifecycle. Refresh tokens are **hashed with bcrypt** before storage, so a leaked DB dump can't be replayed — and logout revokes every issued token at once.

`NestJS` `TypeScript` `PostgreSQL` `TypeORM` `JWT` `Next.js` `React` `Docker`

<details>
<summary>🎓 Earlier projects</summary>

- **Student Course Registration** — enrolment portal with auth, course management, and AJAX updates · `PHP` `MySQL` `JavaScript`
- **[2D Platformer](https://github.com/Hosamtarde/MyUnityGame)** — side-scrolling game with component-based movement and interaction logic · `C#` `Unity`
- **Library Management** — console app for cataloguing and lending · `Python`
</details>

---

## 🛠️ How I Work

| | |
|---|---|
| 🗃️ **Migrations** | Every schema change is a numbered migration — never auto-sync |
| 🛡️ **Security** | Helmet, rate limiting, tighter login throttling, role guards on sensitive endpoints |
| ✅ **Validation** | DTO whitelisting — anything unexpected is rejected before it reaches a service |
| 📐 **Consistency** | One shape for errors, one for success — the frontend never guesses |
| 📖 **Docs** | Live Swagger at `/api/docs` |
| 🔀 **Workflow** | Feature branches → PR review → merge, with Conventional Commits |

---

## 🏆 Achievements

- 🥇 **IEEE-Xtreme 18.0** — ranked **1323 / 8,784** teams worldwide
- 🎓 Member of the **IEEE Student Branch** and **Code Academy**
- 🤝 Attended **Connect 360** (Ramallah) and joint training programs with Birzeit & Khadouri universities

---

## 📊 GitHub Stats

<p align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=Hosamtarde&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" />
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Hosamtarde&layout=compact&theme=tokyonight&hide_border=true&langs_count=6" />
</p>

<p align="center">
  <img src="https://streak-stats.demolab.com?user=Hosamtarde&theme=tokyonight&hide_border=true" />
</p>

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=Hosamtarde&theme=tokyo-night&hide_border=true&area=true" />
</p>

---

<p align="center">
  <b>Have a backend that needs building, or a team that needs a hand?</b><br/>
  📫 <a href="mailto:tardehosam@gmail.com">tardehosam@gmail.com</a> · 🌐 <a href="https://hosamtarade.com">hosamtarade.com</a>
</p>

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=100&section=footer" />
</p>
