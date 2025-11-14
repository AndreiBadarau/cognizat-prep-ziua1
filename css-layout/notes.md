box model = content + padding + border + margin

width - latimea contentului
padding - spatiu in interior, intre content si border
border - conturul boxului
border-radius - arc-ul de cerc al conturului boxului
margin - spatiu in exterior, fata de ce e in jur

width: 30px
margin: 20px auto; - sus/jos 20px, stanga/dreapta auto -> se centreaza
la margin putem scrie noi margin-top de exemplu sa scriem marginea doar pentru top

display: block / inline / inline-block
block - ocupa toata latimea disponibila, incepe de pe linie noua( ex: div, p, h1)
inline - ocupa doar cat continutul, nu poti seta width/height( ex: span, link)
inline-block - se comporta ca inline( sta pe aceeasi linie cu alte elemente), dar poti seta width/height/padding/margin

display: flex; - transforma un element intr-un flex container, activand flexbox layoutului, acest lucru permite:

1. Aranjarea flexibila a copiilor, elementele copil devin "flex items" si pot fi aliniate si distribuite pe axe
2. Control pe asa principala: implicit, copiii se aranjeaza pe orizontala(row)
3. Aliniere usoara: poti folosi justify-content, align-items, gap pentru spacing si aliniere
4. Responsive: Copiii pot creste/micsora cu flex-grow, flex-shrink, flex-basis

justify-content: flex-start / center / space-between / flex-end
flex-start - elementele continutului vor fi lipite de inceput
center - elementele continutului vor fi centrate
space-between - primul la inceput, ultimul la sfarsit si restul cu spatiu egal intre ele
flex-end - elementele continutului vor fi lipite de sfarsit

flex-direction: row / column
row(default) - elementele sunt dispuse pe linie
column - elementele sunt dispuse pe verticala

align-items: flex-start / center / flex-end (axa perpendicualara)
controleaza alinierea elementolor copii pe axa transversala in flexbox sau grid

Dacă flex-direction: row (default) → aliniază vertical (sus/jos)
Dacă flex-direction: column → aliniază orizontal (stânga/dreapta)

stretch (default) - copiii se întind pe toată înălțimea/lățimea
center - centrează copiii pe axa transversală
flex-start - aliniază la început
flex-end - aliniază la sfârșit
baseline - aliniază după linia de bază a textului
