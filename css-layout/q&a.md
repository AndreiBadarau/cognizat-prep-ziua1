1. Întrebări de bază (trebuie să le știi PERFECT)

Ce este CSS și la ce folosește?

CSS vine de la cascading style sheets, este limbajul care stilizeaza si organizeaza paginile web. Face paginile web mai placut din punct de vedere vizual si user-friendly.

Ce înseamnă „separation of concerns” în contextul HTML + CSS?

Separation of concerns poate fi inteles ca si principiul proiectarii software unde codul sursa e separat in straturi si componente, fiecare avand functionalitati distincte cu cat mai putine suprapuneri posibil.

Care sunt metodele prin care poți include CSS într-o pagină HTML?

Exista 3 metode, prima ar fi cea externa, external css, se pune in <head></head>, <link rel="stylesheet" href="styles.css">, a doua ar fi cea interna, internal css, se pune <head></head>, <style> body {background: blue} </style>, a treia ar fi cea inline, pusa direct pe element, <div style="color: red;"></div>

Ce este box model-ul în CSS?

Box-modelul este conceptul fundamental in CSS care descrie cum este calculat spatiul ocupat de fiecare element HTML.

Ce înseamnă content, padding, border, margin?

Content este continutul efectiv(text, imagini etc.), padding este spatiul in interior, intre content si border, border este marginea vizibila a elementului, margin este spatiul exterior transparent intre element si alte elemente

Cum centrezi un div pe orizontală în interiorul altui element?

Sunt mai multe metode, una ar fi cu margin auto, in .child { margin: 0 auto;}, daca face parte dintrun flexbox, putem pune display: flex si justify-content: center

Care e diferența între display: block, inline și inline-block?

Diferentele principale, pentru block, ocupa toata latimea disponibila din parinte, incepe pe linie noua, pentru inline, ocupa doar spatiul necesar continutului si poate sta pe aceeasi linie cu alte elemente inline, pentru inline-block, ii o combinatine de amandoua

Cum faci textul bold? Dar italic?

Pentru a face textul bold, italic etc. , o putem face cu ajutorul "font-style: bold / italic" pe care il adaugam in stylesheetul textului

Ce înseamnă font-family? Ce e un „fallback font”?

Font-family specifica fontul, folosit pentru text. Poti lista mai multe fonturi separate prin virgula, browserul va incerca sa foloseasca primul font disponibil, fallback font ii fontul de rezerva folosit daca cel principal nu este disponibil pe sistemul utilizatorului

Care e diferența între id și class în CSS?

ID-ul este unic, doar un element per pagina, iar class este reutilizabil, diferenta intre cele doua, la id, il selectezi cu #exemplu, iar class cu .exemplu

Cum scrii un selector după:

tag, simplu, doar scriem numele elementului, exemplu: p {}

clasă, cu punct in fata numelui clasei

id? cu #

Ce este line-height și la ce ajută?

Cu line-height poti seta distanta intre linii

Ce face proprietatea overflow? Ce valori cunoști (hidden, scroll, auto)?

Overflow controleaza ce se intampla cu continutul daca depaseste dimensiunile containerului, visible, continutul iese din container, hidden, continutul este taiat, scroll, apare bara de scroll, auto, scroll bar apare doar cand e necesar

2. Selectori & specificitate

3. Cum scrii un selector pentru: „toate paragrafele din interiorul unui div cu clasa .card”?

.card p {
/_ stiluri _/
}

15. Cum selectezi doar copiii direcți ai unui element (> vs spațiu)?

A B → toate elementele B din interiorul lui A (la orice nivel).

A > B → doar elementele B care sunt copii direcți ai lui A.

16. Ce este specificitatea în CSS?

Specificitatea este un sistem de „priorități” prin care browserul decide ce regulă CSS câștigă când mai multe se aplică aceluiași element.
Pe scurt: id > class > tag, iar regulile mai specifice câștigă.

17. Cum se compară ca specificitate: tag, clasă, id, !important?

Ordinea de putere:

!important (dar doar între declarații pe aceeași proprietate),

selectori cu id (#header),

selectori cu clase / pseudo-clase (.card, :hover),

selectori de tag (div, p).

Întotdeauna încerc să evit !important dacă se poate.

18. Ce se întâmplă dacă două reguli CSS se bat cap în cap pentru același element?

Browserul alege:

regula cu specificitate mai mare,

dacă specificitatea e egală, câștigă regula scrisă mai jos în fișier (ultima definită).

19. Selectori pentru:

toate elementele cu clasa .error în interiorul unui form:

form .error { ... }

primul copil al unui ul:

ul li:first-child { ... }

20. Ce este o pseudo-clasă? Exemple.

O pseudo-clasă descrie o stare specială a unui element.

Exemple:
:hover, :active, :focus, :visited, :first-child, :nth-child(2).

21. Ce este un pseudo-element? Exemple.

Un pseudo-element reprezintă o parte a unui element care nu există ca nod HTML separat.

Exemple:
::before, ::after, ::first-line, ::first-letter.

22. Cum ai stiliza doar link-urile la hover?

a:hover {
color: red;
text-decoration: underline;
}

3. Layout: box model, position, float

4. Explică în detaliu box modelul.

Fiecare element este o „cutie” cu:

content,

padding,

border,

margin.

Dimensiunea totală e:
width + padding st/dr + border st/dr + margin st/dr (similar pe verticală).
Așa controlezi layout-ul și spațierile.

24. Diferența între margin și padding (cu exemplu).

padding = spațiu în interior, între conținut și border (mărește „cutia” din interior).

margin = spațiu în exterior, între element și ce e în jur.

Ex: un card cu text lipit de border → măresc padding; dacă vreau spațiu între carduri → măresc margin.

25. Ce este „margin collapsing”?

La elemente block, marginile verticale ale elementelor vecine sau părinte–copil se pot „contopi” într-o singură margine, cu valoarea celei mai mari.
Se întâmplă doar pe verticală (sus/jos), nu pe orizontală.

26. Valorile pentru position și ce fac:

static (default) – elementul stă în fluxul normal.

relative – rămâne în flux, dar îl poți muta relativ la poziția lui inițială (top/right/bottom/left).

absolute – iese din flux și se poziționează relativ la cel mai apropiat părinte poziționat (non-static).

fixed – se poziționează relativ la fereastra browserului (rămâne fix la scroll).

sticky – combinație între relative și fixed: stă normal până atinge un anumit punct, apoi „se lipește”.

27. Cum poziționezi un element în colțul din dreapta-sus al paginii?

Un mod simplu:

.box {
position: fixed;
top: 0;
right: 0;
}

Sau față de un părinte:

.parent {
position: relative;
}

.child {
position: absolute;
top: 0;
right: 0;
}

28. Ce este z-index și când are efect?

z-index controlează ordinea pe axa Z (ce element stă „deasupra”).
Funcționează doar pe elemente poziționate (position diferit de static).
Valori mai mari → elementul apare peste cele cu valori mai mici.

29. Ce înseamnă „containing block” pentru un position: absolute?

Este elementul față de care se calculează coordonatele top/right/bottom/left.
În mod normal, e cel mai apropiat strămoș care are position diferit de static.
Dacă niciun părinte nu e poziționat, se raportează la pagina (viewport/document).

30. La ce se foloseau float și clear? Le mai folosești azi?

Istoric, float se folosea pentru layout (coloane) și pentru a plasa imagini în text.
clear era folosit pentru a opri elementele să se înfășoare în jurul celor float.
Azi, layout-ul se face mai ales cu Flexbox și Grid, iar float se folosește rar, mai mult pentru layout-uri vechi sau cazuri simple (imagine în text).

4. Flexbox

5. Ce este Flexbox și de ce a fost introdus?

Flexbox este un modul de layout 1D care facilitează alinierea și distribuirea spațiului între elemente într-o singură direcție (rând sau coloană).
A fost introdus pentru a rezolva problemele layout-urilor făcute cu float, tabele, etc., și pentru a simplifica alinierea pe orizontală/verticală.

32. Cum activezi Flexbox pe un container?

.container {
display: flex;
}

Toți copiii direcți devin flex-items.

33. Care este axa principală și axa perpendiculară?

Axa principală (main axis) depinde de flex-direction:

row → orizontală,

column → verticală.

Axa perpendiculară (cross axis) este perpendiculară pe axa principală.

34. Ce face flex-direction?

Setează direcția în care sunt aranjate flex-item-urile:

row (default) – de la stânga la dreapta,

row-reverse,

column – de sus în jos,

column-reverse.

35. Ce face justify-content? Exemple.

Aliniază item-urile de-a lungul axe principale.

Valori uzuale:

flex-start – la începutul axei,

center – centrate,

flex-end – la final,

space-between – primul la început, ultimul la final, spațiu egal între,

space-around – spațiu egal în jurul fiecărui item,

space-evenly – spațiu egal între și la margini.

36. Ce face align-items?

Aliniază item-urile pe axa perpendiculară (cross-axis).

Valori uzuale:

stretch (default) – întinde item-urile,

flex-start,

center,

flex-end.

37. Diferența între align-items și align-content.

align-items – aliniază item-urile în cadrul unei singure linii de flex.

align-content – aliniază liniile de flex între ele (are efect doar când există mai multe linii, deci cu flex-wrap: wrap;).

38. Ce face flex-wrap și când l-ai folosi?

Permite item-urilor să „treacă” pe linie nouă când nu mai au loc:

nowrap (default) – totul pe o singură linie,

wrap – item-urile se împart pe mai multe rânduri,

wrap-reverse.

Folositor la galerii de carduri, tag-uri care trebuie să curgă pe mai multe linii etc.

39. Cum centrezi un element pe verticală și orizontală cu Flexbox?

.parent {
display: flex;
justify-content: center; /_ pe axa principală _/
align-items: center; /_ pe axa perpendiculară _/
}

Dacă flex-direction: row;, asta înseamnă centrare orizontală + verticală.

40. Ce face proprietatea gap într-un container flex?

Definește spațiul dintre flex-item-uri, fără să trebuiască să pui margin pe fiecare.
Funcționează și pe Flexbox și pe Grid.

41. Ce înseamnă flex-grow, flex-shrink, flex-basis?

flex-grow – cât de mult poate crește item-ul când există spațiu liber.

flex-shrink – cât de mult poate scădea când spațiul e prea mic.

flex-basis – dimensiunea de bază (înainte de grow/shrink).

Poți folosi prescurtarea: flex: grow shrink basis;
Ex: flex: 1 0 200px;.

5. CSS Grid

6. Ce este CSS Grid?

Grid este un sistem de layout 2D, gândit pentru a organiza elementele în rânduri și coloane în același timp. E ideal pentru layout-uri complexe de pagină.

43. Cum definești 3 coloane egale?

.container {
display: grid;
grid-template-columns: repeat(3, 1fr);
}

1fr = o fracțiune din spațiul disponibil.

44. Ce face grid-template-columns și grid-template-rows?

grid-template-columns – definește structura coloanelor (număr și lățime).

grid-template-rows – definește structura rândurilor (număr și înălțime).

45. Ce face gap în Grid?

La fel ca în Flexbox: definește spațiul dintre celule (rânduri și coloane).
Ai și row-gap, column-gap dacă vrei separat.

6. Culori, unități, background

7. Formate de culori:

#rrggbb – hex (ex: #ff0000),

rgb(r, g, b) – rgb(255, 0, 0),

rgba(r, g, b, a) – cu transparență,

hsl(h, s%, l%) – hue, saturation, lightness,

hsla(...) – cu alpha.

47. Ce e rgba și la ce e util „a”?

rgba = Red, Green, Blue, Alpha.
a este alpha, nivelul de transparență între 0 (complet transparent) și 1 (complet opac).
Util pentru efecte semi-transparente, overlay-uri etc.

48. Tipuri de unități: absolute vs relative.

Absolute: px – dimensiune fixă.

Relative:

% – procent din dimensiunea părintelui,

em – relativ la font-size-ul elementului (sau părintelui),

rem – relativ la font-size-ul root-ului (html),

vh – procent din înălțimea viewport-ului,

vw – procent din lățimea viewport-ului.

49. Diferența între em și rem.

em – relativ la font-size-ul elementului curent (sau părintelui său).

rem – relativ la font-size-ul elementului root (html), indiferent de nesting.

Cu rem e mai ușor să eviți efectul de „mărire în lanț” dacă ai multe nivele.

50. Ce face background-image? Dar background-size: cover vs contain?

background-image setează o imagine de fundal pentru element.

background-size: cover – imaginea acoperă complet elementul, poate fi decupată.

background-size: contain – imaginea încape complet în element, fără decupare, dar pot apărea zone libere.

51. Cum pui o imagine de fundal pe tot ecranul, decupată corect?

body {
margin: 0;
min-height: 100vh;
background-image: url('img.jpg');
background-size: cover;
background-position: center;
background-repeat: no-repeat;
}

7. Responsive & media queries

8. Ce înseamnă „responsive design”?

Un design care se adaptează la dimensiuni și tipuri de ecrane diferite (telefon, tabletă, desktop), astfel încât pagina să rămână utilizabilă și lizibilă peste tot.

53. Ce este un „breakpoint”?

Un punct de lățime (de ex. 768px) la care schimbi layout-ul / stilurile prin media queries, pentru a adapta designul.

54. Media query simplu pentru ecrane sub 600px:

@media (max-width: 600px) {
/_ stiluri pentru ecrane mici _/
}

55. Ce ai schimba pe mobil vs desktop?

De exemplu:

layout-ul din 2 coloane → pe mobil le pui una sub alta,

mărimea fonturilor mai mare,

spațiere mai mare între butoane,

meniul orizontal devine meniu vertical / „burger menu”.

56. Diferența între max-width și min-width în media query.

max-width: 600px – stilurile se aplică până la 600px (ecrane mai mici).

min-width: 600px – stilurile se aplică de la 600px în sus (ecrane mai mari).

min-width e uzual în abordarea „mobile-first”.

57. Ce este „mobile-first CSS”?

Strategia în care:

scrii întâi stilurile pentru ecrane mici (mobile),

apoi adaugi media queries cu min-width pentru ecrane mai mari.

Thus, designul de bază e optimizat pentru mobil.

58. Rolul meta-ului viewport:

<meta name="viewport" content="width=device-width, initial-scale=1.0" />

Spune browserului să folosească lățimea reală a device-ului și să nu „micșoreze” site-ul ca pe desktop.
E esențial pentru ca responsive design-ul să funcționeze corect pe mobil.

8. Fonts, text, UI

9. Cum schimbi fontul unui site?

body {
font-family: "Roboto", Arial, sans-serif;
}

De obicei import fontul (ex. Google Fonts) și îl setez pe body.

60. Ce face text-align?

Aliniază textul în interiorul elementului:

left, right, center, justify.

61. Cum faci textul să apară cu „…” când e prea lung?

.text {
white-space: nowrap;
overflow: hidden;
text-overflow: ellipsis;
}

62. Ce face white-space: nowrap?

Previne ruperea pe linii noi – tot textul stă pe o singură linie, până apare overflow.

63. Cum îmbunătățești lizibilitatea textului pe mobil?

mărire font-size (ex: min 16px),

line-height 1.4–1.6,

spațiere mai mare între paragrafe,

contraste bune între text și background,

margini/padding ca textul să nu fie lipit de marginea ecranului.

9. Animații și tranziții

10. Ce este transition? Exemplu.

Permite schimbări line (animate) între două stări CSS.

button {
background: blue;
transition: background 0.3s ease;
}

button:hover {
background: darkblue;
}

65. Ce este o animație CSS (@keyframes)?

O animație definită prin keyframes (etape), pe care o aplici cu animation.
Ex:

@keyframes fade-in {
from { opacity: 0; }
to { opacity: 1; }
}

.box {
animation: fade-in 1s ease-in;
}

66. Cum faci un buton să-și schimbe culoarea lin în 1 secundă la hover?

button {
background-color: blue;
transition: background-color 1s;
}

button:hover {
background-color: green;
}

10. Practic + debugging

11. Cum verifici ce stiluri se aplică unui element?

Folosesc DevTools în browser (Inspect Element):

selectez elementul,

în pane-ul „Styles” văd toate regulile, ce fișier le conține și care sunt suprascrise.

68. Cum afli de ce o regulă nu se aplică?

verific în DevTools dacă e „tăiată” (overridden),

compar specificitatea celorlalte reguli,

verific ordinea fișierelor CSS,

mă asigur că selectorul chiar potrivește elementul.

69. Cum te asiguri că un design arată bine pe mai multe dimensiuni?

redimensionez fereastra,

folosesc „responsive mode” în DevTools,

testez diferite breakpoints (mobil, tabletă, desktop),

mă uit dacă textul rămâne lizibil și elementele nu se suprapun.

70. Ce faci când un layout se strică pe mobil, dar e ok pe desktop?

verific media queries (poate condiția e greșită),

verific lățimi fixe în px care nu încap pe ecrane mici,

folosesc unități relative (%, vw, rem),

mă uit după elemente care au overflow sau care nu se micșorează corect.

11. Întrebări de tip design real

Aici nu există un singur răspuns corect – îți dau un mod rezonabil de a explica.

71. Cum ai construi layout-ul pentru o pagină de login?

Aș avea:

un container central cu formularul de login (email, parolă, buton),

fundal simplu, cu formularul centrat (Flexbox: justify-content: center; align-items: center;),

pe mobil, formularul ar ocupa aproape toată lățimea (max-width 400–500px, width: 100%),

stiluri clare pentru input-uri și butoane, mesaj de eroare sub ele.

72. Cum ai construi o navbar cu logo stânga, meniu dreapta, mobil vertical?

Pe desktop:

un header cu un container Flexbox:

logo la stânga,

listă de linkuri la dreapta (display: flex, gap).

justify-content: space-between.

Pe mobil (sub 600px):

cu media query schimb flex-direction: column,

logo sus, meniul devine listă verticală,

eventual un buton de „meniu” pentru a ascunde/arăta link-urile.

73. Cum faci layout cu sidebar stânga + content dreapta, pe mobil una sub alta?

Pe container: display: flex;.

Sidebar cu o lățime fixă sau flex: 0 0 250px;, content flex: 1;.

În media query pentru ecrane mici: flex-direction: column;, astfel încât sidebar-ul să apară deasupra sau dedesubtul conținutului.

74. Cum te asiguri că un buton arată „clickable”?

folosesc contrast bun față de fundal,

culoare clară + border-radius mic,

cursor: pointer;,

efect de hover (schimb ușor culoarea, shadow),

padding suficient (click target mare),

text clar (ex: „Trimite”, „Login”).
