---
title: Programming for the Web
subject: Software Engineering
type: final
unit: Year 12
syllabus_topic: Programming for the Web
tags:
  - software-engineering
  - web
  - hsc
  - final
  - exam-ready
  - year-12
aliases:
  - Web Programming
  - Client vs Server
  - Networking
---

# Programming for the Web — HSC Final Notes

> **Year 12, Unit 4** | Client vs server-side, networking, big data, W3C standards, version control, server-side programming, secure web services, databases and web algorithms.

---

## 1. Client-Side vs Server-Side Programming

### 1.1 The Core Distinction

| | **Client** | **Server** |
|---|---|---|
| What it is | "Your device, like your phone or computer" | "A powerful computer that stores and manages websites" |
| Restaurant analogy | Your interaction with the restaurant | The kitchen staff preparing your meal |
| Does | Displays the webpage, handles user interactions, runs JavaScript | Retrieves information from a database, processes requests, generates content |
| Languages | **JavaScript, HTML, CSS** | **PHP, Java, Python, Ruby on Rails** (Node.js is server-side JavaScript) |

**The three client-side languages:**

- **HTML** displays **structure**
- **CSS** makes it **look right** (presentation)
- **JavaScript** makes it **interactive** (behaviour)

**Worked division of labour:**

| Site | Client handles | Server handles |
|---|---|---|
| YouTube | Rendering the UI, handling clicks | Storing videos, processing search |
| E-commerce | Displaying cart and checkout | Managing the database, processing transactions securely |

### 1.2 Full-Stack Development

| Layer | Technologies |
|---|---|
| **Browser** (front end) | JavaScript, jQuery, Angular, Vue |
| **Server** (back end) | PHP, ASP, Python, Node |
| **Database** | SQL, SQLite, MongoDB |

**Common stacks:**

- **MERN** = MongoDB, Express, React, Node
- **MEAN** = MongoDB, Express, Angular, Node

### 1.3 Progressive Web Apps (PWAs)

Client-side capabilities: interactivity, **dynamic updates without reload**, **offline** operation via **service workers**, and local storage (IndexedDB / LocalStorage).

> **Confusing pair — Client-side vs Server-side rendering**
> **Client-side**: the server sends data, and the browser builds the page. Faster after first load, but needs a capable device.
> **Server-side**: the server builds the finished HTML and sends it. Better for slow devices and search-engine indexing, but each interaction needs a round trip.

### 1.4 Front-End Web Development Frameworks

> **NESA note**: "Students should understand **why** such frameworks are useful in front-end web development. Students are **not** expected to have knowledge of a specific framework nor to code using any specific framework."

**Why frameworks are useful**: reusable components, consistent structure, faster development, tested and maintained code, built-in routing and state management, large community support.

---

## 2. Networking

### 2.1 Hardware

| Device | Function | Analogy |
|---|---|---|
| **Hub** | Data in and out through **one** cable; slow; small networks | "A road where all cars meet at an intersection" |
| **Switch** | Many in and out; directs traffic intelligently; large networks and offices | "Traffic lights" |
| **Router** | Finds the "best way" for data; connects to the internet | "Sat-Nav" |
| **Bridge** | Connects two **same** networks | — |
| **Gateway** | Connects two **different** networks | — |

> **Confusing pair — Bridge vs Gateway**
> **Bridge** joins two networks of the **same** type (same protocol).
> **Gateway** joins two **different** networks and translates between protocols.

> **Confusing pair — Hub vs Switch**
> A **hub** broadcasts data to **every** connected device — wasteful and insecure.
> A **switch** sends data **only to the intended device** — faster and more secure.

### 2.2 Topologies

| Topology | Structure |
|---|---|
| **Star** | All devices connect to a **central device** |
| **Ring** | Circular, data travels in **one direction** |
| **Bus** | Single line with **terminators** at each end |
| **Hybrid** | A combination of the above |
| **Wireless** | No physical cabling (e.g. Starlink) |
| **Mesh** | Devices interconnect with multiple paths (e.g. GPS) |

**Worked classifications**: bus = lift control · ring = driverless metro · mesh = GPS · cloud = social media · client-server = online games

### 2.3 MAC vs IP Addresses

| | **MAC address** | **IP address** |
|---|---|---|
| Nature | **Permanent** — burned into the hardware | **Changes** depending on connection |
| Purpose | Identifies the physical device | Identifies the device's location on a network |

Both show "where a computer is located." Highest IPv4 = `255.255.255.255`; IPv6 uses hexadecimal (`FFFF…`).

### 2.4 DNS

> **DNS** is "like a **phone book** for the internet — it translates a website name into an IP address."

- **Primary DNS** is asked first
- **Secondary DNS** holds a copy if the primary is unavailable

### 2.5 Packets and Packet Switching

> Packet switching ensures "data packets get to their destination on time and as free of errors as possible — **even if sent out of sequence**."

**Every packet contains:**

1. **Source address**
2. **Destination address**
3. **Sequence number** (so packets can be reassembled in the right order)

Packet structure is often described as **header** (addressing), **body/payload** (the data) and **tail/footer** (error checking).

### 2.6 Protocols and Ports

| Protocol | Port | Use |
|---|---|---|
| **HTTP** | **80** | General websites |
| **HTTPS** | **443** | Banking and secure sites |
| **FTP** | **21** | File transfer |
| **SMTP** | **25** | **Sends** mail |
| **POP** | — | **Collects** email |
| **DNS** | **53** | Name resolution |
| **SSH** | **22** | Secure shell (cloud and enterprise) |
| **SSL/TLS** | — | Encrypts connections |

> "**Closing unnecessary ports helps prevent attacks**" — every open port is a potential entry point.

**Development ports**: local dev servers often use `localhost:3000`; APIs commonly run front-end on 3000 and back-end on 5000, requiring **CORS** management.

> **CORS (Cross-Origin Resource Sharing)**: a browser security rule that blocks a page from requesting data from a *different* origin (domain/port) unless that server explicitly permits it. This is why a front end on port 3000 cannot call a back end on port 5000 without configuration.

### 2.7 The Browser–Server Request Lifecycle

```
1. User enters a URL
2. DNS lookup resolves the domain to an IP address
3. HTTP/HTTPS request sent to that IP
4. Server responds with files (HTML, CSS, JS, images)
5. Browser renders:
     • DOM interpreter   (builds the page structure)
     • CSS interpreter   (applies styling)
     • JavaScript engine (executes behaviour, using JIT compilation)
```

### 2.8 tcpdump

A command-line **packet capture** tool showing IPs, ports and protocols. Used for debugging traffic, checking ports 80/443, diagnosing SSL/TLS problems and investigating performance.

---

## 3. Big Data

### 3.1 The Six V's

> "**Velocity, volume, value, variety, veracity and variability** — the six main and innate characteristics of big data."

| V | Meaning |
|---|---|
| **Volume** | The sheer quantity of data |
| **Velocity** | The speed at which it is generated and must be processed |
| **Variety** | The range of formats — text, image, video, sensor |
| **Veracity** | How **trustworthy and accurate** the data is |
| **Value** | Whether the data can produce useful insight |
| **Variability** | How the meaning and structure of the data **change over time** |

> **Confusing pair — Veracity vs Variability**
> **Veracity** = can I **trust** this data? (accuracy, reliability)
> **Variability** = does its **meaning or format keep changing**? (inconsistency over time)

### 3.2 The Data Hierarchy

| Level | Definition | Example |
|---|---|---|
| **Data** | "Raw facts or values with **no context**" | Log-in timestamps |
| **Information** | "Data that has been **processed** to make meaning" | A chart of peak log-in hours |
| **Knowledge** | "Insights formed by **analysing** information" | Users log in after school |
| **Understanding** | "Ability to **apply** knowledge to make decisions" | Adjust server load for 3–5pm |

| Term | Definition |
|---|---|
| **Data mining** | "Automatically analysing large data sets to detect trends or patterns" |
| **Metadata** | "**Data about data** — descriptive details" (file size, date created, author) |

### 3.3 Web Mining

| Type | What it analyses |
|---|---|
| **Content mining** | Text, images, audio, video — using text mining, ML and NLP |
| **Structure mining** | How pages **link** to each other (nodes and edges). **Google's ranking uses this** |
| **Usage mining** (log mining) | Clicks, time on page, navigation paths |

### 3.4 What Social Media Collects

Location · device info · contacts · search history · message metadata · likes, comments and shares · browsing history · ad interactions · time spent · uploaded media · age and account details · **biometric info** (face patterns)

### 3.5 Social and Ethical Issues

Data **privacy** · data **security** · data **validation** · data **accuracy** · data **sanitisation**

> **Data sanitisation** = removing or masking sensitive information from a dataset before it is stored, shared or processed. It is also a **security** control — sanitising user input prevents injection attacks (see [[Secure_Software_Architecture]]).

### 3.6 Effect on Web Architecture

**Scale examples**: Facebook (500 TB/day) · YouTube (300 hours of video/minute) · Amazon (up to 2.5M price changes/day; **35% of sales from recommendations**) · Netflix · Starbucks

**Architectural requirements**: data warehouses and analytics servers · **CDNs** (content delivery networks) · real-time streaming protocols (**HLS**, **DASH**) · machine learning and metadata layers

> **Worked application — "TuneMatch"**: data mining (listen, skip and playlist behaviour) · metadata (artist, album, genre, mood, year) · streaming delivered in **small chunks**.

---

## 4. W3C and Web Standards

**W3C** exists to "develop **open, consistent standards** so the World Wide Web stays accessible, reliable, and works the same across all browsers, devices and countries." It works with governments, universities, companies, browser developers and accessibility groups.

**Standards produced**: HTML · CSS · XML · SVG · **WCAG** (accessibility) · Web APIs · browser and security specifications

**Why standards matter**: "Ensures websites work consistently, reduces compatibility issues, improves accessibility, supports global languages, increases long-term stability."

### 4.1 The Need for Standards — the class scenario

> Design a new web-based robot-control language for use on other planets, with **no standards**. Anyone could invent arbitrary syntax, making **interoperability impossible**. This is the argument for W3C and standardisation.
>
> Required keywords in the exercise: `detectObstacle`, `moveForward`, `moveBackward`, `moveLeft`, `moveRight`, `stopRobot`, `startRobot`, `armForward`, `armBackward`, `armGrab`, `armPlaceInTray`.

### 4.2 Web Accessibility Initiative (WAI)

Guidelines and tools for users with disabilities — **visual, hearing, mobility and cognitive**.

**Assistive tools**: screen reader · screen magnifier · speech-to-text · sticky keys

### 4.3 Internationalisation (i18n)

Support for different **languages and scripts without redesign**.

**Affects**: UTF-8 character encoding · left-to-right and **right-to-left** text direction · language tags
**Supports**: Arabic and Hebrew (RTL scripts)

> **Why "i18n"?** There are **18 letters** between the "i" and the "n" in "internationalisation".

### 4.4 Privacy vs Security

> "**Privacy** is about **rights** — who should be allowed to see data. **Security** provides the **technical measures** (e.g. encryption, authentication) that enforce it."

**Relevant standards**: Threat Modelling · WebAuthn · Federated Identity · Web Payment Security

### 4.5 Validation

`validator.w3.org` checks HTML and CSS against the published standards.

### 4.6 CSS Syntax

> **NESA**: "Students are expected to **interpret code fragments** written in CSS and HTML."

```css
/* Comment */
selector {
    property: value;
}
```

| Element | Meaning |
|---|---|
| **Comment** | Anywhere in CSS, enclosed in `/*` and `*/` |
| **Selector** | Targets a particular HTML element for styling |
| **Property** | A styling property, such as `color` |
| **Value** | The value of that property, such as `red` |

**Worked example — the HTML:**

```html
<html>
  <head><title>My Website</title></head>
  <body>
    <h1>Welcome!</h1>
    <p id="welcome">Welcome to my website!</p>
    <p class="red-text">This text should be red</p>
    <p>My website also has <span class="red-text">red text</span> here</p>
  </body>
</html>
```

**The CSS that styles it:**

```css
/* This selector targets an HTML element */
h1 {
   font-size: 18px;
}

/* This selector targets an HTML element with a specific "id" */
#welcome {
   font-style: italic;
}

/* This selector targets an HTML element with a specific "class" */
.red-text {
   color: red;
}
```

> **The three selector types — memorise the punctuation**
> **`h1`** (no symbol) → targets an **element type** — every `<h1>` on the page.
> **`#welcome`** (hash) → targets a single unique **id**. An id should appear **once** per page.
> **`.red-text`** (dot) → targets a **class**. A class can be used **many times**, and on **different element types** (note it applies to both a `<p>` and a `<span>` above).

---

## 5. Version Control and Open-Source Development Tools

### 5.1 Version Control

> "Version control **keeps track of changes made to files over time**, so you can return to a previous version if something goes wrong." It saves snapshots called **commits**.

| Git/GitHub term | Meaning |
|---|---|
| **Fork** | A copy of a repository in your own account |
| **Repository (repo)** | The project folder plus its complete history |
| **README** | The documentation file describing the project |
| **Commit** | A saved change, with a message describing it |
| **Push (to origin)** | Uploading commits to GitHub |
| **Branch** | A parallel line of development |
| **Merge** | Combining changes from one branch into another |

### 5.2 Distributed vs Centralised

| | **Distributed** | **Centralised** |
|---|---|---|
| Examples | **Git, GitHub, GitLab** | **SVN** |
| Structure | Every developer has a **full copy** of the history | One central server holds the history |
| Offline work | Possible | Requires server access |

### 5.3 Why Version Control Matters — the class scenario

> The "**Missing Feature Disaster**" shows the failure modes without version control: USB-stick version confusion, merge chaos, accidental deletion, and no backup.

### 5.4 Open-Source Development Tools

> "**Source code is publicly available.** Anyone can view, modify, improve, share and build tools on top of it."

| Category | Examples |
|---|---|
| **Front-end** | React, Vue, Angular, Svelte, Tailwind, Bootstrap |
| **Back-end** | Node, Express, Django, Flask, Rails, PHP/Laravel |
| **Database** | MySQL, PostgreSQL, MongoDB, SQLite |
| **Infrastructure** | Linux, Docker, Nginx, Apache |

---

## 6. Server-Side Programming and Content Management Systems

### 6.1 The Web Server

> "A web server is a giant computer that holds all the website's content. **Dynamic behaviour is handled by server-side programming.**"

Server-side languages — Python, PHP, Java — "interact with the database and **generate the HTML the browser sees**."

### 6.2 MVC Architecture

| Component | Responsibility |
|---|---|
| **Model** | The **data** and business logic |
| **View** | What the **user sees** — the interface |
| **Controller** | **Handling requests** and coordinating between model and view |

> **The flow**: a request hits the **Controller** → the Controller asks the **Model** for data → the Model returns it → the Controller passes it to the **View** → the View renders the page.
> **Why separate them?** Each part can be changed independently — you can redesign the interface without touching the data logic.

### 6.3 Content Management Systems

> A **CMS** is "like a website builder — templates, tools and features to add pages, images and text."

**Examples**: WordPress, Drupal, Joomla

**Advantage**: "Easier to create and manage content, **even without extensive programming experience**."

### 6.4 Framework Comparison (PMI)

| Framework | Language | Plus | Minus |
|---|---|---|---|
| **React** | JavaScript (Meta) | Component-based, **Virtual DOM** | Steep learning curve; "just a library" — usually paired with Next.js |
| **Angular** | JS/TypeScript (Google) | **Strong typing**, enterprise-grade | Steep, verbose |
| **Express.js** | JavaScript (Node) | Minimalist, flexible, fast; the "E" in MEAN/MERN | Unopinionated; callback hell |
| **Django** | Python | Rapid, secure, scalable; built-in **ORM** | Steep, monolithic, not ideal for real-time |
| **Flask** | Python | Lightweight, easy to learn | Not ideal for complex projects; lacks built-in DB and auth |
| **WordPress** | PHP | Easy, huge community | Security concerns; not ideal for complex apps |
| **Joomla** | PHP | Secure, scalable, multi-language | Steep; fewer themes |

### 6.5 Database Connectivity — worked example

Node + Express + MySQL:

```javascript
const connection = mysql.createConnection({ /* credentials */ });

app.get('/', (req, res) => {
    connection.query('SELECT name, address FROM customers', (err, rows) => {
        res.render('index', { customers: rows });   // rendered via EJS
    });
});
```

---

## 7. Relational Databases and SQL

> **NESA syntax for the HSC Software Engineering course.**

```sql
SELECT    the field(s) or calculated values to be displayed
FROM      the table(s) to be used
WHERE     the search criteria
GROUP BY  the field(s) used to group the returned rows
ORDER BY  the field(s) that determine the sequence of displayed results
```

The keyword **`AS`** may be used within a `SELECT` statement to **rename fields** for display.

### 7.1 Relational Operators

`CONTAINS` · `DOES NOT CONTAIN` · `EQUALS` · `NOT EQUAL TO` · `GREATER THAN` · `GREATER THAN OR EQUAL TO` · `LESS THAN` · `LESS THAN OR EQUAL TO`

### 7.2 Logical Operators

`AND` · `OR` · `NOT`

### 7.3 Aggregate Functions (used with `GROUP BY`)

`SUM(attribute)` · `AVG(attribute)` · `COUNT(attribute)` · `MAX(attribute)` · `MIN(attribute)`

### 7.4 Sort Order

`ASC` (ascending: A–Z or 0–9) · `DEC` (descending: Z–A or 9–0)

### 7.5 Worked Queries

**Query 1** — display the name and release date of all games released from 1 March 2022 to 31 March 2023, in ascending alphabetical order by name:

```sql
SELECT Name, Release_date
FROM Games
WHERE Release_date >= '01/03/2022' AND Release_date <= '31/03/2023'
ORDER BY Name ASC
```

**Query 2** — display each developer with the total cost of games they developed for the publisher 'Games Inc', in descending order of developer name:

```sql
SELECT Developers.First_name, Developers.Last_name, SUM(Games.cost) AS Totalcost
FROM Games, Publishers, Developers
WHERE Publishers.Name = 'Games Inc'
AND Publishers.Publisher_ID = Games.Publisher_ID
AND Developers.Developer_ID = Games.Developer_ID
GROUP BY Developers.Developer_ID
ORDER BY Developers.Last_name DESC
```

> **Reading query 2**: The `WHERE` clause does two different jobs. `Publishers.Name = 'Games Inc'` **filters**; the two `ID = ID` lines **join** the three tables together. Without the join conditions, the query would pair every game with every publisher and every developer.

### 7.6 Object-Relational Mapping (ORM)

> "ORM provides a **layer of abstraction between the database and the programming language**. In an object-oriented language, an ORM will usually represent database **items (rows) as objects** and the **attributes of that item (columns) as properties** of the object."

**Students are expected to interpret code fragments used in an ORM framework.**

| Database concept | ORM equivalent |
|---|---|
| Table | Class |
| Row | Object |
| Column | Property / attribute |

> **Why use an ORM?** You write normal object code instead of SQL strings, it reduces SQL injection risk, and it makes the code portable between database systems. The cost is a performance overhead and less control over the exact query.

---

## 8. Secure Web Services

### 8.1 SSL and TLS

- **SSL** (Netscape, 1995) encrypts data between the site and the user, and verifies identity via a **handshake** ("like a digital signature")
- **TLS** replaced SSL and is **more secure**
- "Websites that use SSL or TLS have **HTTPS**"

### 8.2 The TLS Handshake

```
1. TCP connection established
2. Client sends "client hello"  → cipher suites + TLS version
   Server sends "server hello"  → SSL certificate (public key, hostname, expiry)
   Client validates the certificate
3. Client generates a SESSION KEY, encrypts it with the server's PUBLIC key
   Server decrypts it with its PRIVATE key
4. Both now hold the same symmetric SESSION KEY → encrypted channel
```

> **Why the switch from asymmetric to symmetric?** Asymmetric encryption is **slow** but solves the problem of exchanging a key safely. Symmetric encryption is **fast** but needs both sides to already share a key. TLS uses asymmetric encryption **once**, to deliver the symmetric session key — then uses fast symmetric encryption for the rest of the conversation. Best of both.

### 8.3 Encryption Types

| Type | Key | Use | Example |
|---|---|---|---|
| **Hash functions** | **No key** | Integrity, digital signatures. Produces a fixed-length fingerprint; changes completely on a tiny input change | MD5, SHA-256 |
| **Symmetric-key** | **Same key** both ways | Fast bulk encryption; problem is **secure key distribution** | **AES** — the "gold standard", 128-bit blocks |
| **Asymmetric / public-key** | **Public + private** pair | Secure communication and digital signatures | RSA |

> **Encryption** = scrambling data into unreadable **ciphertext**, decipherable only with a key.
> **Hashing is one-way** — you cannot un-hash a value. That is why it is used for integrity and password storage, not for sending secret messages.

### 8.4 Authentication vs Authorisation

| | Definition |
|---|---|
| **Authentication** | "Checking access **credentials** against a database or list" — proving *who you are* |
| **Authorisation** | "Permits certain usernames/passwords **access to connect**" — determining *what you may do* |

> "You can have **authentication without authorisation**, but you **cannot have authorisation without authentication**."
> You must know who someone is before you can decide what they're allowed to do.

### 8.5 Digital Signatures

```
SENDER:    hash the message  →  encrypt the hash with the sender's PRIVATE key
                             →  send message + signature

RECEIVER:  decrypt the signature with the sender's PUBLIC key
           hash the received message independently
           if the two hashes match  →  INTEGRITY + AUTHENTICITY confirmed
```

> **Note the key order is reversed from encryption.** To keep a message **secret** you encrypt with the recipient's **public** key. To **sign** a message you encrypt with your own **private** key — because only you have it, anyone decrypting successfully with your public key proves it came from you.

### 8.6 Cross-Site Scripting (XSS)

> **NESA definition**: "Cross-site scripting (XSS) involves **injecting malicious code into an otherwise safe website**. It is usually done through **user input that is not sufficiently sanitised** before being processed and stored on the server."

**Students should be able to interpret fragments of JavaScript related to cross-site scripting.**

**The defence**: **input sanitisation and validation** — never trust user input; escape or strip anything that could be interpreted as code before storing or displaying it.

---

## 9. Web Algorithm Description

### 9.1 The IPO Model

| Stage | Content |
|---|---|
| **Input** | Keyboard, mouse, files |
| **Process** | Maths, decisions |
| **Output** | Pictures, graphs, changed data |

> **IPSO** adds **Storage** — used for PWAs that persist data between sessions.

### 9.2 Methods of Algorithm Description

- **Structured English** — numbered steps in plain language
- **Flowcharts** — Start/Stop, Process, Decision, Input/Output, Flow line

### 9.3 Control Structures in JavaScript

| Structure | JavaScript |
|---|---|
| **Sequence** | Logical steps one after another |
| **Selection** | Binary (two options) or multiway (more than two): `if / else if / else` |
| **Repetition** | Pre-test (condition at top) or post-test (condition at bottom): `for` (fixed count), `while` (while true) |

**Operators**: `==` `<` `>` `<=` `>=` `!=` `!` `&&` `||`

### 9.4 JavaScript Data and Storage

**Variables**: `let`, constants, arrays. **Types**: String, Integer, Float.

| Web storage | Use |
|---|---|
| **`localStorage`** | Small text and numbers; persists indefinitely |
| **`sessionStorage`** | Persists only **until the tab is closed** |
| **`IndexedDB`** | Large **structured** data; works offline |
| **`Cache API`** | Cached resources for offline use |

### 9.5 Output Types

| Type | Method |
|---|---|
| **Text** | `console.log`, `alert` |
| **Visual** | `textContent` |
| **Sound** | `new Audio().play()` |
| **Haptic** | `navigator.vibrate` |
| **Notification** | Notification API |
| **Data** | API response |

---

## 10. Caesar Cipher

### 10.1 The Definition as Given

> "A Caesar cipher is a type of **substitution cipher** in which each letter in the plaintext is replaced by a letter some fixed number of positions **down the alphabet**. For example, with a **left shift of 3**, D would be replaced by A, E would become B."

### 10.2 ⚠️ Known Error in the Starter Document

> **Your `Software Links.txt` flags this**: *"Starter 2 — Caesar Cipher and Terminology Revision — THE DOCUMENT IS WRITTEN WRONG. In order to decrypt a left shift of 1 you would move 1 to the right…"*

**The specific inconsistency**: the text calls it a "**left shift of 3**" and the example (D→A, E→B) is **correct for a left/backward shift**, but it describes the substitution as moving "**down the alphabet**" — which normally means *forward* toward Z (D→G), the opposite direction.

**The word "down" should read "up" or "back."**

> **The rule to actually use**
> **Encrypt** with a left shift of *n* → move each letter *n* places **backwards** (toward A).
> **Decrypt** a left shift of *n* → move each letter *n* places **forwards** (toward Z).
> Encryption and decryption always move in **opposite** directions.

### 10.3 Implementation

```python
def decrypt_left_shift_1(ch):
    return chr((ord(ch) - ord('a') - 1) % 26 + ord('a'))
```

> The `% 26` handles **wrap-around** — so that shifting back from 'a' lands on 'z' rather than a non-letter character.

### 10.4 Worked Decryption Table (left shift of 1)

The decrypted words are all networking terminology — this doubles as revision for §2.

| Ciphertext | Plaintext | Ciphertext | Plaintext |
|---|---|---|---|
| Ivc | **Hub** | Upqpmphz | **Topology** |
| Txjudi | **Switch** | Qbdlfu txjudijoh | **Packet Switching** |
| Spvufs | **Router** | Ifbe | **Head** |
| Csjehf | **Bridge** | Cpez | **Body** |
| Hbufxbz | **Gateway** | Gppufs | **Footer** |
| Tubs | **Star** | Ubjm | **Tail** |
| Sjoh | **Ring** | IUUQT | **HTTPS** |
| Cvt | **Bus** | GUQ | **FTP** |
| Xjsfmftt | **Wireless** | TNUQ | **SMTP** |
| QPQ | **POP** | TTM | **SSL** |

> *One row in the source ("Python → Tail") is misaligned; the correct mapping is `Ubjm` → Tail.*

**Consistency check**: the W3 activities use the same convention — `Uifsf jt b tfdsfu dpef!` → "There is a secret code!" (shift 1); `Khoor Zruog!` → "Hello World!" (shift 3).

---

## 11. HSC Exam Response Structures

### Common Question Types

| Question type | How to answer |
|---|---|
| **"Distinguish client-side from server-side"** | Define both → name languages for each → give a worked division of labour for a real site |
| **"Explain the TLS handshake"** | Four numbered stages → emphasise the asymmetric-to-symmetric switch and **why** |
| **"Interpret this SQL query"** | Read clause by clause: what's displayed (SELECT) → from where (FROM) → filters vs joins (WHERE) → grouping → sort order |
| **"Interpret this CSS fragment"** | Identify each selector type by its punctuation → state which HTML elements it targets → state the styling applied |
| **"Explain how XSS occurs and how to prevent it"** | Define XSS → unsanitised user input stored and re-served → defence is input sanitisation and validation |
| **"Justify the use of version control in a team"** | Define commits → name the failure modes without it → link to collaboration factors |
| **"Evaluate the six V's for [scenario]"** | Take each V, apply it to the specific data described, then judge which pose the biggest challenge |

### Paragraph Scaffold

```
Topic sentence (define the term)
  → explain the mechanism (how the protocol/technology actually works)
  → apply to a scenario (your project, or the case in the question)
  → link to a syllabus concept (security, standards, accessibility, scalability)
```

---

## 12. Glossary — Terms Students Mix Up

| Term | Plain meaning | Don't confuse with |
|---|---|---|
| **Client-side** | Runs in the **browser** | **Server-side** — runs on the server |
| **Hub** | Broadcasts to every device | **Switch** — sends only to the target |
| **Bridge** | Joins two **same** networks | **Gateway** — joins **different** networks |
| **MAC address** | **Permanent** hardware identifier | **IP address** — changes with connection |
| **DNS** | Translates names to IP addresses | DHCP (assigns IP addresses) |
| **SMTP** | **Sends** mail (port 25) | **POP** — **collects** mail |
| **HTTP (80)** | Unencrypted | **HTTPS (443)** — encrypted with TLS |
| **Veracity** | Can the data be **trusted**? | **Variability** — does its meaning change? |
| **Data** | Raw facts, no context | **Information** — processed to make meaning |
| **Knowledge** | Insight from analysing information | **Understanding** — applying it to decide |
| **Metadata** | Data **about** data | The data itself |
| **Structure mining** | How pages **link** (Google ranking) | **Content mining** — the page contents |
| **Privacy** | About **rights** — who *should* see data | **Security** — technical measures enforcing it |
| **i18n** | Supporting many languages/scripts | Localisation (adapting to one specific locale) |
| **`#id` selector** | Targets **one** unique element | **`.class`** — reusable, many elements |
| **Fork** | Copy of a repo in your account | **Branch** — a parallel line in the same repo |
| **Commit** | A saved snapshot with a message | **Push** — uploading commits to the remote |
| **Distributed VCS** | Everyone has full history (Git) | **Centralised** — one server (SVN) |
| **Model** | Data and logic | **View** — the interface; **Controller** — request handling |
| **CMS** | Website builder for non-programmers | Framework (a coding toolkit) |
| **Symmetric encryption** | Same key both ways; **fast** | **Asymmetric** — public/private pair; slow |
| **Hashing** | **One-way**, no key, for integrity | Encryption (reversible with a key) |
| **Authentication** | Proving **who you are** | **Authorisation** — what you're **allowed** to do |
| **Digital signature** | Encrypt hash with **private** key | Encryption for secrecy uses the **public** key |
| **SSL** | The original protocol (1995) | **TLS** — its more secure replacement |
| **XSS** | Injecting malicious script via unsanitised input | SQL injection (targets the database) |
| **ORM** | Maps tables to classes, rows to objects | Raw SQL |
| **`localStorage`** | Persists indefinitely | **`sessionStorage`** — cleared when tab closes |
| **CORS** | Browser rule on cross-origin requests | A server firewall |

---

## 13. Key Definitions Quick Reference

| Term | One-Line Definition |
|---|---|
| Client | The user's device that displays the page and handles interaction |
| Server | A powerful computer that stores data, processes requests and generates content |
| Full-stack | Browser + server + database development |
| PWA | Web app with offline capability via service workers |
| Hub | Connects devices via one cable, broadcasting to all |
| Switch | Directs data only to the intended device |
| Router | Finds the best path for data; connects to the internet |
| Bridge | Connects two networks of the same type |
| Gateway | Connects two different networks |
| MAC address | Permanent hardware identifier |
| IP address | Network address that changes with connection |
| DNS | Translates domain names into IP addresses |
| Packet switching | Sending data in packets that can arrive out of sequence |
| Big data | Data characterised by the six V's |
| Data mining | Automatically analysing large data sets to detect patterns |
| Metadata | Data about data |
| Web content mining | Analysing text, images, audio and video |
| Web structure mining | Analysing how pages link together |
| Web usage mining | Analysing clicks, time and navigation paths |
| W3C | Body developing open, consistent web standards |
| WCAG | Web Content Accessibility Guidelines |
| WAI | Web Accessibility Initiative |
| i18n | Internationalisation — supporting many languages and scripts |
| Version control | Tracking changes to files over time through commits |
| Commit | A saved change with a descriptive message |
| Repository | A project folder plus its complete history |
| Open source | Source code publicly available to view, modify and share |
| MVC | Model (data), View (interface), Controller (requests) |
| CMS | A website builder requiring little programming experience |
| SQL | Language used to access and manipulate relational databases |
| ORM | Abstraction layer mapping database rows to program objects |
| SSL / TLS | Protocols encrypting data between site and user |
| TLS handshake | Exchange establishing a shared symmetric session key |
| Hash function | One-way, keyless transformation used for integrity |
| Symmetric encryption | Same key to encrypt and decrypt; fast (AES) |
| Asymmetric encryption | Public and private key pair |
| Digital signature | Hash encrypted with the sender's private key |
| Authentication | Checking credentials to prove identity |
| Authorisation | Determining permitted level of access |
| XSS | Injecting malicious code via unsanitised user input |
| Caesar cipher | Substitution cipher shifting each letter a fixed number of places |
| IPO / IPSO | Input–Process–Output, plus Storage |

---

## 14. Quick Revision Checklist

- [ ] Client vs server, with languages and a worked division of labour
- [ ] MERN and MEAN stacks
- [ ] Five network devices, especially bridge vs gateway and hub vs switch
- [ ] Six topologies with an example each
- [ ] MAC vs IP; DNS primary and secondary
- [ ] The three things every packet contains
- [ ] All eight protocols and their port numbers
- [ ] The five-step browser–server request lifecycle
- [ ] The six V's, with veracity vs variability distinguished
- [ ] Data → information → knowledge → understanding, with examples
- [ ] Three types of web mining
- [ ] W3C purpose, WCAG, WAI tools, i18n
- [ ] Interpret a CSS fragment — element, `#id` and `.class` selectors
- [ ] Git terms; distributed vs centralised
- [ ] MVC and what each component does
- [ ] Write and interpret SQL with SELECT/FROM/WHERE/GROUP BY/ORDER BY
- [ ] Aggregate functions and the AS keyword
- [ ] Explain ORM and the table/row/column → class/object/property mapping
- [ ] The four-stage TLS handshake and why it switches asymmetric → symmetric
- [ ] Three encryption types; hashing is one-way
- [ ] Authentication vs authorisation, and the one-way dependency
- [ ] Digital signature steps and the reversed key order
- [ ] XSS definition and prevention
- [ ] Four web storage options
- [ ] Caesar cipher, including the flagged error in the starter document

---

> **See also:** [[Software_Automation]] | [[Secure_Software_Architecture]] | [[Programming_Fundamentals]] | [[Object_Oriented_Programming]] | [[Mechatronics]] | [[MOC]]
