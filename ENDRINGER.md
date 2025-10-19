# Detaljert Endringsoversikt - Carbon Footprint Nettside

## Oversikt
Dette dokumentet beskriver alle endringene som ble gjort for å gjøre nettsiden mer profesjonell og brukervennlig. Endringene inkluderer forbedret design, bedre fargevalg, elegant typografi, og en mer konsistent brukeropplevelse på tvers av hele nettsiden.

**Siste oppdatering:** Dempet lyse hvite farger på register/login sider for bedre kontrast

---

## 0.1.11 Dempet Hvite Farger på Register/Login (NYT!)

### Hva ble gjort?
Endret de lyse hvite fargene på register/login-sidene til mykere, mørkere nyanser for å redusere lysstyrken og forbedre kontrasten mot den mørke grønne bakgrunnen.

### Hvor finnes dette?
**Fil:** `capp/static/user.css` (linjer 85, 102, 115, 148, 163, 216)

### Detaljer:

**Input-felter:**
- **Bakgrunn (normal):** Fra `var(--light-bg)` (#f8fafc) til `#e2e8f0` - Mykere lys grå
- **Bakgrunn (fokus):** Fra `var(--white)` (#ffffff) til `#f1f5f9` - Veldig lys grå i stedet for ren hvit
- **Tekstfarge:** Beholdt mørk slate `#1e293b` for god lesbarhet

**Tekst-elementer:**
- **Overskrift (legend):** Fra `var(--text-white)` (#ffffff) til `#e2e8f0` - Lys grå
- **Labels:** Fra `var(--text-light)` (#e2e8f0) til `#cbd5e1` - Mørkere grå
- **Border-tekst:** Fra `var(--text-light)` til `#cbd5e1` - Mørkere grå
- **Checkbox labels:** Fra `var(--text-light)` til `#cbd5e1` - Mørkere grå

### CSS-kode:
```css
/* Input-felter - dempede farger */
.register_section_css .form-control {
  background-color: #e2e8f0 !important; /* Var: #f8fafc */
  color: #1e293b !important;
}

.register_section_css .form-control:focus {
  background-color: #f1f5f9 !important; /* Var: #ffffff */
}

/* Tekst - mørkere grå */
.register_section_css legend {
  color: #e2e8f0 !important; /* Var: #ffffff */
}

.form-control-label {
  color: #cbd5e1; /* Var: #e2e8f0 */
}

.register_section_css .border-top {
  color: #cbd5e1 !important; /* Var: #e2e8f0 */
}
```

### Hvor du ser endringen:
- ✅ Input-felter: Mykere grå bakgrunn i stedet for knallhvit
- ✅ Overskrift ("Join Today"): Lys grå i stedet for ren hvit
- ✅ Labels og tekst: Mørkere grå for bedre kontrast
- ✅ Generelt mindre blendende/skarp kontrast
- ✅ Mer behagelig å se på

### Hvorfor denne endringen?
- **Mindre lysintensitet:** Hvite felter kan være blendende mot mørk bakgrunn
- **Bedre kontrast:** Mørkere grå tekst står bedre frem
- **Mer profesjonelt:** Dempede farger ser mer sofistikerte ut
- **Bedre brukeropplevelse:** Mindre anstrengende for øynene

---

## 0.1.10 Solide Knappefarger (NYT!)

### Hva ble gjort?
Fjernet alle gradienter fra knapper som hadde mørk grønn-til-svart gradient på hover. Endret til solid mørk grønn farge (`var(--secondary-green)`) for en renere og mer moderne stil.

### Hvor finnes dette?
**Filer:**
- `capp/static/methodology.css` (linje 122)
- `capp/static/carbon_app.css` (linjer 123 og 137)
- `capp/static/home.css` (linjer 318 og 327)
- `capp/static/about_us.css` (linjer 127 og 137)
- `capp/static/user.css` (linjer 192 og 199)

### Detaljer:

**Knapper på Methodology-siden:**
- **Før hover:** `linear-gradient(135deg, var(--secondary-green) 0%, var(--primary-dark) 100%)`
- **Etter hover:** `var(--secondary-green)` - Solid mørk grønn

**Knapper på Carbon App-siden:**
- **Før hover:** `linear-gradient(135deg, var(--secondary-green) 0%, var(--primary-dark) 100%)`
- **Etter hover:** `var(--secondary-green)` - Solid mørk grønn

**Curriculum-knapper (Home & About Us):**
- **Før:** `linear-gradient(135deg, var(--primary-light) 0%, var(--primary-green) 100%)`
- **Etter:** `var(--primary-green)` - Solid grønn
- **Før hover:** `linear-gradient(135deg, var(--primary-green) 0%, var(--secondary-green) 100%)`
- **Etter hover:** `var(--secondary-green)` - Solid mørk grønn

**Login/Register knapper:**
- **Før:** `linear-gradient(135deg, var(--primary-light) 0%, var(--primary-green) 100%)`
- **Etter:** `var(--primary-green)` - Solid grønn
- **Før hover:** `linear-gradient(135deg, var(--primary-green) 0%, var(--secondary-green) 100%)`
- **Etter hover:** `var(--secondary-green)` - Solid mørk grønn

**Modal header:**
- **Før:** `linear-gradient(135deg, var(--primary-dark) 0%, var(--primary-green) 100%)`
- **Etter:** `var(--primary-green)` - Solid grønn

### CSS-kode:
```css
/* Methodology knapper */
.container_buttons_links_header a:hover {
  background: var(--secondary-green) !important;
}

/* Carbon App knapper */
.container_buttons_links_header_carbon_app a.btn:hover {
  background: var(--secondary-green) !important;
}

/* Curriculum knapper */
.btn_developers {
  background: var(--primary-green);
}

.btn_developers:hover {
  background: var(--secondary-green);
}

/* Login/Register knapper */
.register_section_css .btn-outline-info {
  background: var(--primary-green) !important;
}

.register_section_css .btn-outline-info:hover {
  background: var(--secondary-green) !important;
}

/* Modal header */
.modal-header {
  background: var(--primary-green) !important;
}
```

### Hvor du ser endringen:
- ✅ Methodology-side: Knapper har solid grønn farge ved hover
- ✅ Carbon App-side: Knapper har solid grønn farge ved hover
- ✅ Curriculum-knapper på Home & About Us: Solid grønn, mørk grønn ved hover
- ✅ Login/Register-knapper: Solid grønn, mørk grønn ved hover
- ✅ Modal-vinduer: Header har solid grønn bakgrunn
- ✅ Ingen gradienter på noen knapper lenger

### Hvorfor denne endringen?
- **Renere design:** Solid farger ser mer profesjonelle ut enn gradienter
- **Moderne stil:** Minimalistisk design uten distraherende gradienter
- **Konsistens:** Alle knapper bruker nå samme stil
- **Bedre lesbarhet:** Enklere farger gjør innholdet lettere å fokusere på

---

## 0.1.9 "Meet Our Team" på Hjemmesiden (NYT!)

### Hva ble gjort?
Erstattet "Explore More" seksjonen (med navigasjonsbokser) på hjemmesiden med "Meet Our Team" seksjonen som viser alle teammedlemmer. Team-seksjonen er fortsatt på About Us-siden også.

### Hvor finnes dette?
**Filer:**
- `capp/templates/home.html` (linjer 49-122) - HTML endringer
- `capp/static/home.css` (linjer 246-331 og responsive styles) - CSS oppdateringer

### Detaljer:
- **Før:** "Explore More" med 3 store navigasjonsbokser (Total Global Emissions, Methodology, About Us)
- **Etter:** "Meet Our Team" med 7 individuelle teammedlem-kort
- Kopieret fullstendig team-seksjon fra About Us-siden
- Oppdatert CSS til å matche about_us.css styling
- Beholder team-seksjonen på About Us-siden

### HTML-struktur:
```html
<section class="section_developers">
 <div class="container">
   <h1>Meet our team!</h1>
   <p>The people who made all of this possible:</p>

   <div class="developers">
     <!-- 7 developer cards -->
     <div class="box">
       <img src="..." alt="...">
       <h3>Name</h3>
       <p>Info</p>
       <a class="btn_developers" href="#">Curriculum</a>
     </div>
   </div>
 </div>
</section>
```

### CSS endringer:
- Byttet fra `.team_boxes` og `.team_box` til `.developers` og `.developers .box`
- Endret fra 3 store bokser i rad til flex-wrap grid med 280px brede kort
- Runde profilbilder (150x150px)
- Hvit bakgrunn med grønn border
- Gradient grønne knapper
- Responsiv design for mobil

### Hvor du ser endringen:
- ✅ Hjemmesiden viser nå alle 7 teammedlemmer nederst
- ✅ About Us-siden beholder sin team-seksjon
- ✅ Konsistent styling mellom begge sidene
- ✅ Kort med profilbilder, navn, info og curriculum-lenke

### Hvorfor denne endringen?
- **Bedre synlighet:** Teammedlemmer vises direkte på hjemmesiden
- **Mer personlig:** Besøkende ser hvem som står bak appen
- **Bedre innhold:** Erstatter navigasjonsbokser (som ikke trengs) med relevant innhold
- **Konsistens:** Samme design på home og about us

---

## 0.1.8 Adaptiv Navbar Tekstfarge (NYT!)

### Hva ble gjort?
Lagt til spesifikke CSS-regler som automatisk endrer navbar-tekstfargen til hvit på sider med mørk bakgrunn (register, login, carbon app, methodology). Dette sikrer god kontrast uansett hvilken side du er på.

### Hvor finnes dette?
**Filer:**
- `capp/static/user.css` (linjer 9-21) - For register/login sider
- `capp/static/carbon_app.css` (linjer 28-39) - For carbon app side
- `capp/static/methodology.css` (linjer 46-57) - For methodology side

### Detaljer:
- **Lyse sider (home, about us):** Mørk grønn tekst (`var(--primary-dark)`)
- **Mørke sider (register, login, carbon app, methodology):** Hvit tekst (`var(--text-white)`)
- Bruker CSS `:has()` selector for å automatisk detektere mørke bakgrunner
- Overskriver tekstfarge med `!important` for å sikre prioritet

### CSS-kode:
```css
/* For register/login sider */
body:has(.register_section_css) .carbon_app_navbar a {
  color: var(--text-white) !important;
}

body:has(.register_section_css) .carbon_app_navbar a:hover {
  color: var(--text-light) !important;
}

body:has(.register_section_css) .carbon_app_navbar .text-logo {
  color: var(--text-white) !important;
}

/* Samme mønster for .section_header_carbon_app og .section_header_methodology */
```

### Hvor du ser endringen:
- ✅ Hjemmesiden: Mørk grønn navbar-tekst (god kontrast mot lys bakgrunn)
- ✅ Register/Login: Hvit navbar-tekst (god kontrast mot mørk grønn bakgrunn)
- ✅ Carbon App: Hvit navbar-tekst (god kontrast mot mørk grønn bakgrunn)
- ✅ Methodology: Hvit navbar-tekst (god kontrast mot mørk grønn bakgrunn)
- ✅ About Us: Mørk grønn navbar-tekst

### Hvorfor denne endringen?
- **Adaptiv design:** Navbar tilpasser seg automatisk til bakgrunnsfargen
- **God kontrast:** Alltid lesbar tekst uansett bakgrunn
- **Ingen manuell styling:** Fungerer automatisk på alle sider
- **Profesjonelt:** Konsekvent lesbarhet på tvers av hele nettsiden

---

## 0.1.7 Mørk Grønn Tekstfarge i Navbar (NYT!)

### Hva ble gjort?
Endret tekstfargen i navbar fra lys hvit til mørk grønn for bedre kontrast og mer profesjonelt utseende mot den transparente bakgrunnen.

### Hvor finnes dette?
**Fil:** `capp/static/layout.css` (linjer 123 og 136)

### Detaljer:
- **Normal tilstand:**
  - **Før:** `color: var(--text-light)` - Lys hvit/grå (#e2e8f0)
  - **Etter:** `color: var(--primary-dark)` - Mørk grønn (#0f4c3a)
- **Hover tilstand:**
  - **Før:** `color: var(--text-white)` - Hvit (#ffffff)
  - **Etter:** `color: var(--secondary-dark)` - Veldig mørk grønn (#1a3a2e)
- **Aktiv side:** Beholder hvit tekst på grønn bakgrunn

### CSS-kode:
```css
/* Navbar lenker - mørk grønn */
.carbon_app_navbar a {
    color: var(--primary-dark);
}

/* Hover - enda mørkere grønn */
.carbon_app_navbar a:hover {
    color: var(--secondary-dark);
}

/* Aktiv side - hvit på grønn */
.carbon_app_navbar a.active {
    background: var(--primary-green);
    color: var(--text-white);
}
```

### Hvor du ser endringen:
- ✅ Navbar-tekst er nå mørk grønn i stedet for lys hvit
- ✅ Bedre kontrast mot transparent bakgrunn
- ✅ Mer profesjonelt og lesbart
- ✅ Ved hover blir teksten enda mørkere grønn

### Hvorfor denne endringen?
- **Bedre kontrast:** Mørk grønn tekst er lettere å lese mot lys bakgrunn
- **Profesjonelt utseende:** Mørkere farger ser mer sofistikerte ut
- **Konsistent:** Matcher den grønne fargepaletten på nettsiden
- **Lesbarhet:** Tydeligere tekst mot transparent navbar

---

## 0.1.6 Navbar Overlay med Absolute Posisjonering (NYT!)

### Hva ble gjort?
Endret navbar til å bruke `position: absolute` i stedet for `fixed`, slik at den overlayer bakgrunnsbildet uten å være sticky. Dette gir en transparent navbar som ligger over bildet, men som ikke følger med ved scrolling.

### Hvor finnes dette?
**Filer:**
- `capp/static/layout.css` (linje 104-108)

### Detaljer:
- **Navbar posisjon:**
  - **Før:** `position: fixed` - Forble øverst ved scrolling
  - **Etter:** `position: absolute` med `top: 0`, `left: 0`, `right: 0` - Overlayer bildet, scroller med siden
- **Body padding:** `padding: 0` - Ingen ekstra padding nødvendig

### CSS-kode:
```css
/* Navbar overlayer bildet transparent */
.section_carbon_app_navbar {
    background: transparent;
    backdrop-filter: none;
    box-shadow: none;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    z-index: 1000;
}
```

### Hvor du ser endringen:
- ✅ Navbar overlayer bakgrunnsbildet transparent
- ✅ Navbar scroller opp og ut av syne når du scroller ned
- ✅ Fullstendig transparent - bakgrunnsbildet vises gjennom
- ✅ Ingen gap mellom navbar og bakgrunnsbilde

### Hvorfor denne endringen?
- **Transparent overlay:** Navbar ligger over bildet uten å blokkere det
- **Mer plass:** Innholdet får hele skjermhøyden når du scroller
- **Moderne design:** Hero-seksjon med transparent navbar over bildet
- **Renere opplevelse:** Navbar flyter naturlig over bakgrunnen

---

## 0.1.5 Fullstendig Transparent Navbar (NYT!)

### Hva ble gjort?
Fjernet all bakgrunnsfarge, blur-effekt og skygge fra navbar for å gjøre den fullstendig transparent. Nå vises bakgrunnsbildet direkte gjennom navbar uten noen filter eller fargelag.

### Hvor finnes dette?
**Fil:** `capp/static/layout.css` (linjer 100-111)

### Detaljer:
- **Bakgrunn:**
  - **Før:** `background: rgba(15, 76, 58, 0.7)` - 70% ugjennomsiktig grønn
  - **Etter:** `background: transparent` - Fullstendig gjennomsiktig
- **Blur-effekt:**
  - **Før:** `backdrop-filter: blur(15px)` - Uskarp bakgrunn
  - **Etter:** `backdrop-filter: none` - Ingen blur
- **Skygge:**
  - **Før:** `box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1)`
  - **Etter:** `box-shadow: none` - Ingen skygge

### CSS-kode:
```css
.section_carbon_app_navbar {
    background: transparent;
    backdrop-filter: none;
    -webkit-backdrop-filter: none;
    box-shadow: none;
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    width: 100%;
    z-index: 1000;
}
```

### Hvor du ser endringen:
- ✅ Navbar har ingen grønn bakgrunn lenger
- ✅ Bakgrunnsbildet vises direkte gjennom navbar
- ✅ Ingen blur-effekt
- ✅ Ingen skygge
- ✅ Fullstendig transparent navbar

### Hvorfor denne endringen?
- **Ren transparens:** Bakgrunnsbildet får skinne fullt igjennom
- **Minimalistisk design:** Ingen lag mellom navbar og bakgrunn
- **Moderne utseende:** Fullstendig gjennomsiktig navbar er et dristig designvalg
- **Fokus på innhold:** Navbar trer tilbake og lar bakgrunnen og innholdet få oppmerksomhet

---

## 0.1.4 Fjernet Gradient fra Navbar (NYT!)

### Hva ble gjort?
Fjernet alle gradienter fra navbar - både hover-effekten og den aktive siden. Nå bruker den aktive siden en solid grønn farge i stedet for en gradient fra lys grønn til mørk grønn.

### Hvor finnes dette?
**Fil:** `capp/static/layout.css` (linjer 135-150)

### Detaljer:
- **Vanlig hover:** `background-color: transparent` - Ingen bakgrunn
- **Aktiv side:**
  - **Før:** `background: linear-gradient(135deg, var(--primary-light) 0%, var(--primary-green) 100%)` - Gradient fra lys til mørk grønn
  - **Etter:** `background: var(--primary-green)` - Solid grønn farge
- **Box shadow:** Fjernet (var `0 2px 8px rgba(34, 197, 94, 0.3)`)

### CSS-kode:
```css
/* Vanlig hover - ingen bakgrunn */
.carbon_app_navbar a:hover {
    background-color: transparent;
    color: var(--text-white);
}

/* Aktiv side - solid grønn farge */
.carbon_app_navbar a.active {
    background: var(--primary-green);
    color: var(--text-white);
    font-weight: 600;
    box-shadow: none;
}

/* Aktiv side hover - samme solide farge */
.carbon_app_navbar a.active:hover {
    background: var(--primary-green);
}
```

### Hvor du ser endringen:
- ✅ Når du holder musen over navbar-lenker, vises ingen bakgrunn
- ✅ Den aktive siden har nå en solid grønn bakgrunn (ikke gradient)
- ✅ Ingen skygge på aktiv side-knapp
- ✅ Renere og mer minimalistisk navbar
- ✅ Fokus på den aktive siden

### Hvorfor denne endringen?
- **Renere utseende:** Solid farge ser mer profesjonell ut enn gradient
- **Bedre fokus:** Den aktive siden skiller seg tydeligere ut
- **Moderne design:** Minimalistisk tilnærming uten gradienter
- **Bedre kontrast:** Enklere farger mot transparent navbar-bakgrunn

---

## 0.1.3 Fjernet Teksteffekter fra Beskrivelsestekst (NYT!)

### Hva ble gjort?
Fjernet tekstskygge og glød-effekter fra beskrivelsesteksten ("A modern platform to calculate...") på hjemmesiden for en renere og mer minimalistisk stil.

### Hvor finnes dette?
**Fil:** `capp/static/home.css` (linje 96)

### Detaljer:
- **Før:** `text-shadow: 2px 2px 6px rgba(0, 0, 0, 0.8), 0 0 15px rgba(0, 0, 0, 0.5)`
- **Etter:** `text-shadow: none`

### CSS-kode:
```css
.hero_content p {
    color: #ffffff !important;
    font-weight: 500 !important;
    text-shadow: none !important;
}
```

### Hvor du ser endringen:
- ✅ Beskrivelsesteksten på hjemmesiden har ikke lenger skygge
- ✅ Renere og mer moderne utseende
- ✅ Teksten er fortsatt godt lesbar mot bakgrunnen

### Hvorfor denne endringen?
- **Renere design:** Mindre visuell "støy" gjør teksten lettere å lese
- **Moderne stil:** Minimalistisk design er trendy og profesjonelt
- **Fokus:** Lar innholdet tale for seg selv uten distraherende effekter

---

## 0.1.2 Universell Bruk av Fargepalett (NYT!)

### Hva ble gjort?
Oppdaterte **ALLE** CSS-filer for å sikre at de bruker CSS-variablene fra den enhetlige fargepaletten i stedet for hardkodede farger. Dette sikrer at hele nettsiden har en konsistent fargebruk på tvers av alle sider.

### Hvor ble dette fikset?
**Filer:**
- `capp/static/user.css` - Register/Login sider
- `capp/static/about_us.css` - Om oss side

### Detaljer:

**user.css (Register/Login):**
- **Bakgrunn:** Byttet fra `#1e293b`/`#0f172a` til `var(--primary-dark)`/`var(--secondary-dark)`
- **Form-boks:** Byttet fra grå/slate farger til grønne CSS-variabler med glassmorfisme-effekt
  - `background: linear-gradient(135deg, rgba(15, 76, 58, 0.95) 0%, rgba(26, 58, 46, 0.95) 100%)`
  - `backdrop-filter: blur(20px)`
- **Input-felter:** Bruker nå `var(--light-bg)`, `var(--text-dark)`, og `var(--primary-light)`
- **Knapper:** Byttet fra hardkodede grønne farger til `var(--primary-light)` og `var(--primary-green)`
- **Tekst:** Alle tekstfarger bruker nå `var(--text-white)`, `var(--text-light)`, `var(--text-medium)`
- **Borders:** Byttet fra grå borders til grønne: `rgba(34, 197, 94, 0.3)`

**about_us.css (Om oss):**
- **Hero-seksjon:** Byttet fra `#b9eccd`/`#8cd6aa` til `var(--primary-green)`/`var(--accent-green)`
- **Tekstfarger:** Byttet fra `#f4f4f4`, `#2c2c2c`, `#444`, `#333` til CSS-variabler
- **Bakgrunner:** Byttet fra `#ffffff`, `#f8f8f8` til `var(--light-bg)` og `var(--white)`
- **Accent-farger:** Byttet fra `#006400`, `#7cc785`, `#68b071` til CSS-variabler
- **Knapper:** Bruker nå gradienter med `var(--primary-light)` og `var(--primary-green)`
- **Shadows:** Alle skygger bruker nå `var(--shadow-sm)`, `var(--shadow-md)`, `var(--shadow-lg)`

### Før og Etter eksempler:

**Før (hardkodede farger):**
```css
/* user.css */
background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
color: #fff;
background-color: #f1f5f9;
border: 2px solid #cbd5e1;

/* about_us.css */
background: linear-gradient(135deg, #b9eccd, #8cd6aa);
color: #006400;
background-color: #7cc785;
```

**Etter (CSS-variabler):**
```css
/* user.css */
background: linear-gradient(135deg, var(--primary-dark) 0%, var(--secondary-dark) 100%);
color: var(--text-white);
background-color: var(--light-bg);
border: 2px solid rgba(34, 197, 94, 0.2);

/* about_us.css */
background: linear-gradient(135deg, var(--primary-green) 0%, var(--accent-green) 100%);
color: var(--primary-dark);
background: linear-gradient(135deg, var(--primary-light) 0%, var(--primary-green) 100%);
```

### Hvor du ser endringen:
- ✅ Register-siden bruker nå samme grønne fargepalett som resten av nettsiden
- ✅ Login-siden matcher register-siden perfekt
- ✅ Om oss-siden bruker nå konsistente grønne farger
- ✅ Alle knapper på tvers av siden har samme stil
- ✅ Alle skygger og borders matcher hverandre

### Hvorfor denne endringen?
- **Konsistens:** Hele nettsiden ser nå enhetlig og profesjonell ut
- **Vedlikehold:** Hvis du vil endre farger i fremtiden, trenger du bare å endre CSS-variablene på ett sted
- **Branding:** Sterk grønn identitet på tvers av hele nettsiden
- **Profesjonalitet:** Ingen "glemte" sider med forskjellige farger

---

## 0.1.1 Transparent Tekstboks med Forbedret Kontrast (NYT!)

### Hva ble gjort?
Fjernet den mørke grønne bakgrunnen fra tekstboksen på hjemmesiden slik at bakgrunnsbildet vises gjennom. Samtidig la vi til kraftige tekstskygger og forbedret fargene for å sikre at all tekst er godt lesbar mot bakgrunnsbildet.

### Hvor finnes dette?
**Fil:** `capp/static/home.css` (linjer 50-145)

### Detaljer:
**Tekstboks (hero_content):**
- **Bakgrunn:** `transparent` - Ingen bakgrunn, fullstendig gjennomsiktig
- **Blur-effekt:** Fjernet (var `blur(20px)`)
- **Skygge:** Fjernet (var stor skygge)

**Tekst kontrast-forbedringer:**
- **Hovedoverskrift (h1):**
  - Hvit farge (`#ffffff`)
  - Dobbel tekstskygge for lesbarhet: `2px 2px 8px rgba(0, 0, 0, 0.8)` og `0 0 20px rgba(0, 0, 0, 0.6)`

- **"Carbon" tekst (highlight):**
  - Lys grønn farge (`#22c55e`)
  - Ekstra skygge med grønn glød: `0 0 30px rgba(34, 197, 94, 0.4)`
  - Drop shadow filter for ekstra dybde

- **Brødtekst (p):**
  - Hvit farge (`#ffffff`)
  - Font-vekt økt til 500 (semi-bold) for bedre lesbarhet
  - Tekstskygge: `2px 2px 6px rgba(0, 0, 0, 0.8)`

**Knapper med forbedret kontrast:**
- **Primærknapp (Get Started):**
  - Grønn gradient med skygge: `0 4px 15px rgba(0, 0, 0, 0.6)`
  - Grønn glød-effekt: `0 0 20px rgba(34, 197, 94, 0.3)`

- **Sekundærknapp (Login):**
  - Semi-transparent hvit bakgrunn: `rgba(255, 255, 255, 0.15)`
  - Hvit tekst og hvit ramme
  - Skygge for dybde

### CSS-kode:
```css
/* Transparent tekstboks */
.hero_content {
    background: transparent !important;
    backdrop-filter: none !important;
    box-shadow: none !important;
}

/* Høykontrast tekst */
.hero_content h1 {
    color: #ffffff !important;
    text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8), 0 0 20px rgba(0, 0, 0, 0.6) !important;
}

.hero_content h1 .highlight {
    color: #22c55e !important;
    text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.8), 0 0 20px rgba(0, 0, 0, 0.6), 0 0 30px rgba(34, 197, 94, 0.4) !important;
    filter: drop-shadow(0 0 10px rgba(34, 197, 94, 0.6)) !important;
}

.hero_content p {
    color: #ffffff !important;
    font-weight: 500 !important;
    text-shadow: 2px 2px 6px rgba(0, 0, 0, 0.8), 0 0 15px rgba(0, 0, 0, 0.5) !important;
}
```

### Hvor du ser endringen:
- ✅ Tekstboksen på hjemmesiden er nå fullstendig transparent
- ✅ Bakgrunnsbildet vises gjennom teksten
- ✅ All tekst har kraftige skygger for god lesbarhet
- ✅ "Carbon" teksten har en grønn glød-effekt
- ✅ Knappene har skygger og står godt frem mot bakgrunnen

### Hvorfor denne endringen?
- **Bedre visuell flyt:** Bakgrunnsbildet får skinne igjennom uten å bli blokkert av en boks
- **Moderne design:** Transparent design med høykontrast tekst er en moderne designtrend
- **Profesjonelt utseende:** Tekst som "flyter" over bildet ser mer sofistikert ut
- **God lesbarhet:** Tekstskygger sikrer at alt er lesbart uansett hva som er i bakgrunnen

---

## 0.1 Gjennomsiktig Navbar med Overlay-Effekt (NYT!)

### Hva ble gjort?
Navbar ble gjort gjennomsiktig med en moderne "glassmorfisme"-effekt (frosted glass) som overlayer over det nye bakgrunnsbildet. Dette gir nettsiden et moderne, profesjonelt utseende der navigasjonsbaren smelter sammen med bakgrunnen på en elegant måte.

### Hvor finnes dette?
**Fil:** `capp/static/layout.css` (linjer 100-111 og 52-62)

### Detaljer:
- **Gjennomsiktig bakgrunn:** `rgba(15, 76, 58, 0.7)` - 70% opasitet
- **Blur-effekt:** `backdrop-filter: blur(15px)` - Gir frosted glass-effekt
- **Posisjon:** `position: fixed` - Navbar forblir øverst ved scrolling
- **Z-index:** `z-index: 1000` - Sikrer navbar alltid er på toppen
- **Body padding:** `padding-top: 70px` - Forhindrer at innhold havner bak navbar

### CSS-kode:
```css
/* Gjennomsiktig navbar med blur-effekt */
.section_carbon_app_navbar {
  background: rgba(15, 76, 58, 0.7);
  backdrop-filter: blur(15px);
  -webkit-backdrop-filter: blur(15px);
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  width: 100%;
  z-index: 1000;
}

/* Body padding for å unngå overlap */
body {
  padding-top: 70px;
}
```

### Hvor du ser endringen:
- ✅ Navbar er nå gjennomsiktig på alle sider
- ✅ Bakgrunnsbildet vises gjennom navbar
- ✅ Blur-effekt gir et frosted glass-utseende
- ✅ Navbar følger med når du scroller ned på siden

### Hvorfor denne endringen?
- **Moderne design:** Glassmorfisme er en populær designtrend i 2024/2025
- **Bedre fokus:** Lar bakgrunnsbildet få mer oppmerksomhet
- **Profesjonelt utseende:** Gir et sofistikert og polert inntrykk
- **Bedre plassbruk:** Bakgrunnsbildet får mer synlighet

---

## 0. Typografi - Profesjonell Font-Kombinasjon (NYT!)

### Hva ble gjort?
Vi implementerte en profesjonell font-kombinasjon med "Playfair Display" for overskrifter og "Source Sans 3" for brødtekst. Dette gir nettsiden et elegant og moderne utseende med utmerket lesbarhet.

### Hvor finnes dette?
**Fil:** `capp/static/layout.css` (linjer 35-36, 53, og 74-78)

### Detaljer:
- **Overskrifter:** Playfair Display (serif)
  - Vekter: 400, 600, 700, 800
  - Brukes på: h1, h2, h3, h4, h5, h6 + logo
- **Brødtekst:** Source Sans 3 (sans-serif)
  - Vekter: 300 (light), 400 (regular), 600 (semi-bold), 700 (bold)
  - Brukes på: Alle paragrafer, knapper, lenker, og vanlig tekst

### Hvorfor denne kombinasjonen?
- **Playfair Display (overskrifter):** Elegant, klassisk serif som fanger oppmerksomhet
- **Source Sans 3 (brødtekst):** Moderne, profesjonell og ekstremt lesbar
- **Kombinasjonen:** Perfekt balanse mellom eleganse og funksjonalitet
- **Profesjonelt utseende:** Mye brukt i profesjonelle nettsider og applikasjoner

### Hvorfor Source Sans 3 i stedet for Roboto?
- Bedre lesbarhet på lange tekstbolker
- Mer profesjonell og sofistikert
- Parer perfekt med Playfair Display
- Moderne og ren design
- Brukes av Adobe og mange profesjonelle nettsider

### Hvor du ser endringen:
- ✅ Logo "FootPrint" i navigasjonsbaren
- ✅ "Carbon App" på hjemmesiden
- ✅ "Carbon App Calculator" på kalkulator-siden
- ✅ "Explore More", "What We Do", etc.
- ✅ "Join Today", "Log In" på skjema-sidene
- ✅ Alle andre overskrifter på nettsiden

### CSS-kode:
```css
/* Import */
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700;800&display=swap');

/* Anvendelse */
h1, h2, h3, h4, h5, h6 {
  font-family: 'Playfair Display', serif;
  font-weight: 700;
  line-height: 1.2;
}
```

---

## 1. Enhetlig Fargepalett (Unified Color Scheme)

### Hva ble gjort?
Vi opprettet et sett med standardfarger som brukes på hele nettsiden. Dette kalles CSS-variabler og sikrer at alle sider ser like ut.

### Hvor finnes dette?
**Fil:** `capp/static/layout.css` (linjer 1-32)

### Fargepaletten:
- **Primærfarger (Grønn)**
  - Mørk grønn: `#0f4c3a` - Brukes til bakgrunner og headere
  - Medium grønn: `#16a34a` - Brukes til knapper og lenker
  - Lys grønn: `#22c55e` - Brukes til høydepunkter og hover-effekter

- **Sekundærfarger**
  - Mørk blågrønn: `#1a3a2e` - Brukes til gradienter
  - Mørk grønn: `#15803d` - Brukes til hover-effekter

- **Nøytrale farger**
  - Mørk bakgrunn: `#1f2937` - For mørke seksjoner
  - Medium bakgrunn: `#334155` - For kort og bokser
  - Lys bakgrunn: `#f8fafc` - For lyse seksjoner
  - Hvit: `#ffffff`

- **Tekstfarger**
  - Mørk tekst: `#1a1a1a` - For tekst på lys bakgrunn
  - Medium tekst: `#4b5563` - For sekundær tekst
  - Lys tekst: `#e2e8f0` - For tekst på mørk bakgrunn
  - Hvit tekst: `#ffffff`

### Hvorfor er dette viktig?
- Alle sider bruker nå samme farger, noe som gjør nettsiden mer profesjonell
- Enklere å endre farger i fremtiden - bare endre på ett sted
- Gir nettsiden en sterk miljø/bærekraft-identitet

---

## 2. Hjemmeside (Home Page) Forbedringer

### Fil: `capp/static/home.css`

### 2.1 Hero-seksjonen (Den store boksen øverst)

**Før:** Hvit boks med hvit tekst (vanskelig å lese)
**Nå:** Mørk grønn boks med hvit/lys tekst (lett å lese)

#### Endringer:
- **Bakgrunn:** Mørk grønn gradient (0f4c3a → 1a3a2e, 95% ugjennomsiktig)
- **Tekst:** Hvit (#ffffff) for overskrift, lys grå (#e2e8f0) for beskrivelse
- **"Carbon" tekst:** Grønn gradient som skiller seg ut
- **Fjernet:** Glødeeffekter, skygger på tekst, grønn ramme rundt boksen
- **Beholdt:** Avrundede hjørner (24px), moderne utseende

### 2.2 Knapper (Get Started og Login)

**Forbedringer:**
- Grønn gradient bakgrunn (22c55e → 16a34a)
- Fjernet skygger/glødeeffekter for et renere utseende
- Knappene løfter seg litt når du holder musen over (hover-effekt)
- Mørkere grønn når du holder musen over

### 2.3 Informasjonskort ("What We Do" og "What's Your Impact?")

**Forbedringer:**
- "What We Do": Hvit bakgrunn med mørk tekst
- "What's Your Impact?": Mørk gradient bakgrunn (1f2937 → 0f4c3a) med hvit tekst
- Bedre spacing og større padding (3rem)
- Smooth hover-effekter som løfter kortene
- Pil-animasjon på "Calculate Emissions" lenke

### 2.4 "Explore More" seksjonen

**Forbedringer:**
- Lys bakgrunn (#f8fafc) for god kontrast
- Tre bokser: "Total Global Emissions", "Methodology", "About Us"
- Methodology-boksen er grønn for å skille seg ut
- Smooth hover-effekter som løfter og skalerer boksene
- Mørk overlay på bilder for bedre tekstlesbarhet

### 2.5 Bakgrunn

**Endring:**
- Fra lys blå/grå gradient til mørk grønn gradient
- Gir en mer profesjonell og miljøvennlig følelse
- Fjernet grønn overlay fra bakgrunnsbildet

---

## 3. Navigasjonsmeny (Navbar)

### Fil: `capp/static/layout.css` og `capp/templates/layout.html`

### Hva ble forbedret?

#### 3.1 Gjennomsiktig Overlay Design (NYESTE OPPDATERING!)
**Før:** Solid mørk grønn gradient
**Nå:** Gjennomsiktig overlay som ligger over bakgrunnsbildet

**Detaljer:**
- **Bakgrunn:** 85% gjennomsiktig mørk grønn (`rgba(15, 76, 58, 0.85)`)
- **Blur-effekt:** `backdrop-filter: blur(10px)` for frosted glass-effekt
- **Position:** `sticky` - følger med når du scroller ned
- **Z-index:** 1000 - sikrer at navbar alltid er på toppen
- **Skygge:** Subtil skygge for å løfte navbar fra innholdet

**Hvorfor er dette bedre?**
- Moderne glassmorfisme-design (frosted glass)
- Ser bakgrunnsbildet gjennom navbar
- Mer elegant og mindre dominerende
- Følger med når du scroller (sticky)
- Professional utseende

**CSS-kode:**
```css
.section_carbon_app_navbar {
  background: rgba(15, 76, 58, 0.85);
  backdrop-filter: blur(10px);
  position: sticky;
  top: 0;
  z-index: 1000;
}
```

#### 3.2 Utseende (Original Design)
**Tidligere:** Lys blå bakgrunn (#b8eccc)
**Før denne oppdateringen:** Solid mørk grønn gradient

#### 3.2 Lenker
- **Farge:** Lys grå tekst (#e2e8f0)
- **Hover:** Lys grønn bakgrunn som viser hvilken lenke du peker på
- **Avrundede hjørner:** 8px for et moderne utseende

#### 3.3 Aktiv Side Indikator (NYT!)
Dette var en av hovedendringene du ba om.

**Hva skjer nå:**
- Når du er på "Register"-siden, får den lenken en **grønn gradient bakgrunn**
- Når du er på "Carbon App"-siden, får den lenken en **grønn gradient bakgrunn**
- Dette gjelder for alle sider: Register, Login, Methodology, Carbon App, About Us

**Hvordan det fungerer:**
- HTML-koden sjekker hvilken side du er på
- Legger til en "active" klasse på riktig lenke
- CSS-en gir denne klassen en grønn bakgrunn

**CSS (layout.css linjer 117-126):**
```css
.carbon_app_navbar a.active {
  background: linear-gradient(135deg, #22c55e 0%, #16a34a 100%);
  color: #ffffff;
  font-weight: 600;
  box-shadow: 0 2px 8px rgba(34, 197, 94, 0.3);
}
```

**HTML (layout.html linjer 57-70):**
Hver lenke har nå kode som sjekker om den er aktiv:
```html
<a href="..." class="{% if request.endpoint == 'users.register' %}active{% endif %}">
```

---

## 4. Carbon App Side

### Fil: `capp/static/carbon_app.css`

### Forbedringer:

#### 4.1 Bakgrunn
- Mørk grønn gradient (0f4c3a → 1a3a2e)
- Gir en profesjonell og konsistent følelse

#### 4.2 Kalkulator-boksen
- Delvis gjennomsiktig bakgrunn med blur-effekt
- Grønn ramme (var ikke synlig før)
- Moderne skygge for dybde

#### 4.3 Knapper (Methodology, Instructions, New Entry, Your Data)
**Før:** Blå knapper (#007bff)
**Nå:** Grønne gradient knapper som matcher resten av siden
- Grønn gradient (16a34a → 15803d)
- Mørkere grønn når du holder musen over
- Konsistent med resten av nettsiden

#### 4.4 Modal (Popup-vindu for Instructions)
- Grønn gradient i headeren
- Hvit bakgrunn i body-delen
- Bedre spacing og moderne utseende

---

## 5. Registrering og Login Sider

### Fil: `capp/static/user.css`

### Hovedforbedringer:

#### 5.1 Bakgrunn
**Før:** Lys blå/grå (#9fa7bf)
**Nå:** Mørk blå-grønn gradient (1e293b → 0f172a)

#### 5.2 Skjemaboks
**Før:** Grønnaktig bakgrunn (#49736f)
**Nå:** Mørk gradient (334155 → 1e293b) med bedre kontrast

#### 5.3 Inputfelt (Tekstbokser)
Dette var et stort problem - teksten var usynlig!

**Løsning:**
- Lys grå bakgrunn (#f1f5f9) i inputfeltene
- Mørk tekst (#1e293b) som er lett å lese
- Hvit bakgrunn når du klikker i feltet
- Grønn ramme når feltet er aktivt (fokus)

#### 5.4 Labels og Tekst
- Lys grå (#e2e8f0) for god lesbarhet på mørk bakgrunn
- Hvite overskrifter
- Grønne lenker for konsistens

#### 5.5 Knapper
- Grønn gradient bakgrunn (22c55e → 16a34a)
- Løfter seg når du holder musen over
- Mørkere grønn på hover

#### 5.6 Feilmeldinger
- Rød bakgrunn for feil
- Grønn bakgrunn for suksess
- Tydelige farger som er lette å se

---

## 6. Responsivt Design (Mobil og Tablet)

Alle endringer fungerer på:
- **Desktop:** Full bredde og alle effekter
- **Tablet (1024px):** Tilpasset layout
- **Mobil (768px):** Vertikal stabling av elementer
- **Liten mobil (480px):** Mindre tekst og kompakte knapper

### Spesifikke tilpasninger:

**Hjemmeside:**
- Hero-tekst blir mindre på mobil
- Infokort stables vertikalt
- "Explore More" bokser stables vertikalt
- Knapper blir smalere

**Navbar:**
- Stables vertikalt på mobil
- Lenker blir mindre
- Aktiv-indikatoren fungerer fortsatt

**Carbon App:**
- Kalkulator-boks og bilde stables vertikalt
- Knapper sentreres
- Tekst blir mindre

**Skjemaer:**
- Sideboksene forsvinner på mobil
- Skjemaboksen tar full bredde
- Inputfelt forblir lesbare

---

## 7. Tekniske Forbedringer

### 7.1 CSS Variabler
- Alle farger er nå definert som variabler (`:root`)
- Gjør det enkelt å endre farger globalt
- Reduserer risiko for feil og inkonsistens

### 7.2 !important Tags
Brukt strategisk for å overstyre Bootstrap's standardstiler:
- Sikrer at våre farger alltid brukes
- Forhindrer at Bootstrap's blå/lilla farger dukker opp
- Nødvendig for inputfelt og knapper

### 7.3 Transitions og Animasjoner
Alle interaktive elementer har smooth overganger:
- 0.3s cubic-bezier easing for profesjonell følelse
- Hover-effekter som løfter elementer
- Fade-in animasjon på hero-boksen

### 7.4 Box Shadows
Tre nivåer av skygger:
- **Small:** Subtile skygger for lette elementer
- **Medium:** Standard skygger for knapper og kort
- **Large:** Dype skygger for modaler og hero-boks

---

## 8. Fjernede Effekter

På forespørsel ble følgende fjernet fra hjemmesiden:

### 8.1 Fjernet Overlay
- Grønn overlay på bakgrunnsbilde (var: rgba(15, 76, 58, 0.7))
- Nå: Transparent overlay som viser originalbilde

### 8.2 Fjernet Glødeeffekter
- Text-shadow på overskrifter
- Drop-shadow på "Carbon" tekst
- Box-shadow på knapper (glødeeffekt)

### 8.3 Fjernet Ramme
- Grønn ramme rundt hero-boks
- Gir et renere, mer minimalistisk utseende

---

## 9. Sammendrag av Filendringer

### Filer som ble endret:

1. **`layout.css`**
   - Lagt til CSS variabler (linjer 1-32)
   - Oppdatert navbar styling
   - Lagt til active state for lenker

2. **`layout.html`**
   - Lagt til active klasse logikk på alle navbar lenker
   - Bruker Flask's request.endpoint for å detektere aktiv side

3. **`home.css`**
   - Komplett redesign av hero-seksjon
   - Oppdatert alle farger til å bruke CSS variabler
   - Forbedret knapper, kort og "Explore More" seksjon
   - Responsivt design forbedringer

4. **`carbon_app.css`**
   - Byttet fra blå til grønn fargepalett
   - Oppdatert alle farger til å bruke CSS variabler
   - Forbedret knapper og modal styling

5. **`user.css`**
   - Komplett redesign av skjema
   - Fikset usynlig tekst i inputfelt
   - Mørk profesjonell bakgrunn
   - Grønne knapper som matcher resten

6. **`methodology.css`** (NYT!)
   - Komplett redesign fra hvitt til profesjonelt mørkt grønt tema
   - Header nå med mørk grønn gradient bakgrunn
   - Oppdatert alle farger til å bruke CSS variabler
   - Forbedret kort, tabeller og knapper
   - Moderne hover-effekter og skygger

---

## 9.1 Methodology Side Forbedringer (NYT!)

### Fil: `capp/static/methodology.css`

### Hva ble endret?
Methodology-siden hadde mye hvitt og så uprofesjonell ut. Vi har nå redesignet hele siden for å matche resten av nettsidens profesjonelle utseende.

### Hovedendringer:

#### Header Seksjon
**Før:** Hvit/lys bakgrunn
**Nå:** Mørk grønn gradient (0f4c3a → 1a3a2e)

- Hvit tekst for god lesbarhet
- Content-boks med hvit bakgrunn og moderne skygger
- Avrundede hjørner (16px)
- Hover-effekt som løfter boksen

#### Body Seksjon
**Før:** Grå bakgrunn (#e7ebf0)
**Nå:** Lys gradient (f8fafc → e8ecf0)

- Bedre kontrast med content
- Mer moderne utseende

#### Content Bokser (box_table1 og box_table2)
**Endringer:**
- **box_table1:** Grønn gradient bakgrunn (22c55e → 16a34a)
- **box_table2:** Hvit/lys gradient med moderne skygger
- Avrundede hjørner (12-16px)
- Hover-effekter som løfter boksene
- Bedre spacing og padding

#### Overskrifter og Tekst
- Overskrifter (h4): Mørkere og tykkere (700 vekt)
- Grønn understrekning på h4 (3px solid)
- Bedre lesbarhet med Source Sans 3 font
- Forbedret linjeavstand (1.7)

#### Knapper
**Før:** Mørk blå
**Nå:** Grønn gradient som matcher resten av siden
- Hover-effekt med mørkere grønn
- Løfter seg ved hover
- Moderne skygger

#### Tabeller (box_table2_grid)
**Forbedringer:**
- Header-rader: Mørk grønn gradient
- Data-rader: Hvit bakgrunn
- Hover: Lys grønn bakgrunn (#f0fdf4)
- Avrundede hjørner på tabellen
- Moderne skygger
- Bedre borders (#e5e7eb)

### CSS-kode eksempler:

**Header:**
```css
.section_header_methodology {
  background: linear-gradient(135deg, var(--primary-dark) 0%, var(--secondary-dark) 100%);
  color: var(--text-white);
}
```

**Content bokser:**
```css
.methodology .box_table1 {
  background: linear-gradient(135deg, var(--primary-light) 0%, var(--primary-green) 100%);
  border-radius: 12px;
  box-shadow: var(--shadow-md);
}
```

**Tabell header:**
```css
.box_table2_grid .grid-box:first-child {
  background: linear-gradient(135deg, var(--primary-dark) 0%, var(--secondary-dark) 100%);
  color: var(--text-white);
}
```

### Resultat:
- ✅ Methodology-siden ser nå profesjonell ut
- ✅ Matcher resten av nettsidens design
- ✅ Bedre lesbarhet og kontrast
- ✅ Moderne hover-effekter og animasjoner
- ✅ Konsistent bruk av grønn fargepalett

### Ekstra Fikser (Oppdatering):
**Problem:** Hvit tekstboks og feil logo-farge

**Løsning:**
- Header tekstboks endret fra hvit til **mørk grønn gradient** (samme som hjemmesiden)
- Logo ("Methodology") endret til **lys grønn** (#22c55e) for synlighet på mørk bakgrunn
- Knapper: Lagt til `!important` for å overstyre inline blå styles fra HTML
- Nå matcher tekstboksen perfekt med resten av siden

**CSS endringer:**
```css
.header .box {
  background: linear-gradient(135deg, rgba(15, 76, 58, 0.95) 0%, rgba(26, 58, 46, 0.95) 100%);
  color: var(--text-white);
}

.section_header_methodology .text-logo {
  color: var(--primary-light); /* Lys grønn for synlighet */
}
```

---

## 10. Hvordan Teste Endringene

### Ting å sjekke:

1. **Navbar:**
   - Klikk på hver lenke (Register, Login, etc.)
   - Den aktive siden skal ha grønn bakgrunn
   - Hover over andre lenker skal vise lys grønn bakgrunn

2. **Hjemmeside:**
   - Tekst i hero-boksen skal være lett å lese (hvit/lys grå)
   - Knapper skal være grønne
   - "Explore More" seksjonen skal ha tre bokser
   - Alt skal se bra ut på mobil

3. **Register/Login:**
   - Skriv i tekstfeltene - teksten skal være synlig (mørk)
   - Bakgrunnen skal være lys grå i feltene
   - Grønn ramme når du klikker i felt
   - Grønn knapp

4. **Carbon App:**
   - Grønn bakgrunn
   - Grønne knapper (ikke blå)
   - Modal skal ha grønn header

5. **Methodology:**
   - Mørk grønn header
   - Hvite content-bokser med moderne skygger
   - Grønne knapper og grønne content-bokser
   - Tabeller med grønn header
   - Hover-effekter fungerer

---

## 11. Fremtidige Forbedringer (Forslag)

Hvis dere vil gjøre flere endringer senere:

### Enkle endringer:
- **Endre farger:** Endre bare i `layout.css` CSS variabler (linjer 4-32)
- **Endre skriftstørrelse:** Endre `font-size` verdier
- **Legge til flere hover-effekter:** Kopier eksisterende hover-kode

### Mer avanserte endringer:
- Legge til animasjoner når du scroller
- Legge til bilder/ikoner i "Explore More" seksjon
- Lage en "dark mode" toggle
- Legge til grafer/statistikk på hjemmesiden

---

## 12. Nøkkelord og Begreper

For fremtidig referanse:

- **CSS Variabler:** Gjenbrukbare verdier (farger, størrelser) definert én gang
- **Gradient:** Gradvis overgang mellom to eller flere farger
- **Hover:** Effekt som skjer når du holder musen over noe
- **Active State:** Indikerer hvilken side/lenke som er aktiv
- **Responsive Design:** Design som tilpasser seg forskjellige skjermstørrelser
- **Box Shadow:** Skygge rundt elementer for å gi dybde
- **Transition:** Smooth animasjon mellom to tilstander
- **!important:** CSS-regel som overstyter andre regler
- **Z-index:** Kontrollerer hvilke elementer som er foran andre
- **Opacity:** Gjennomsiktighet (0 = usynlig, 1 = helt synlig)

---

## 13. Kontaktinformasjon for Feilsøking

Hvis noe ikke fungerer:

### Vanlige problemer:

**Problem:** Endringer vises ikke
**Løsning:** Hard refresh i nettleseren
- Windows/Linux: Ctrl + Shift + R
- Mac: Cmd + Shift + R

**Problem:** Farger ser feil ut
**Løsning:** Sjekk at alle CSS-filer er lastet inn i layout.html

**Problem:** Aktiv side-indikator vises ikke
**Løsning:** Sjekk at Flask's `request` objekt er tilgjengelig

**Problem:** Tekst er usynlig
**Løsning:** Sjekk at `!important` tags er på plass i CSS

---

## Konklusjon

Nettsiden har nå:
- ✅ Enhetlig grønn fargepalett som brukes overalt
- ✅ Profesjonelt og moderne design
- ✅ Tydelig indikator for hvilken side du er på (navbar)
- ✅ Lesbar tekst overalt (før var mye tekst usynlig)
- ✅ Konsistent utseende på alle sider
- ✅ Responsivt design som fungerer på mobil og tablet
- ✅ Smooth animasjoner og hover-effekter
- ✅ Ren og minimalistisk stil uten unødvendige effekter

Nettsiden ser nå mye mer profesjonell ut og gir en sterk miljø/bærekraft-identitet gjennom den konsekvente bruken av grønne farger.
