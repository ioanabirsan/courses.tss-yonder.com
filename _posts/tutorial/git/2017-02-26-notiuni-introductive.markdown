---
layout: post
title: "git - noțiuni introductive"
date: 2017-02-26 20:00:00
author: ["Mircea Brățan", "Alexandru Coman"]
categories: [tutorial, git]
section-type: post
excerpt_separator: <!--more-->
color: blue
highlight: true
---

Pentru a veni în întâmpinarea celor care nu sunt familiarizați cu sistemul de versionare git am pregătit acest tutorial care vă va arăta pașii care trebuie urmați pentru a încărca proiectele voastre pe GitHub.

<!--more-->

## Concepte de bază
Înainte de a începe tutorialul este util să răspundem la câteva întrebări și să definim câteva noțiuni.

### Ce este un sistem de versionare?
Un sistem de versionare este un mod de management al fișierelor care permite păstrarea istoricului tuturor modificărilor aduse fișierelor urmărite. O introducere a tipurilor de sisteme de versionare poate fi citită aici: [git-scm.com](http://git-scm.com/book/en/v2/Getting-Started-About-Version-Control)
În continuare vom discuta despre sisteme de versionare din perspectiva folosirii lor în cadrul proiectelor software.

### Ce este github.com?
GitHub este un serviciu de hosting al proiectelor git (un proiect git este numit `repository`). Acesta permite păstrarea unei copii a proiectului online și vizualizarea tuturor fișierelor și a modificărilor aduse acestora.

### Care sunt avantajele folosirii unui sistem de versionare?
* este salvat istoricul tuturor modificărilor, astfel că se poate reveni oricând la o versiune mai veche dacă se descoperă introducerea unor defecte în ultima versiune
* prin folosirea unui serviciu de hosting, codul sursă are mereu o copie de siguranță online
* cea mai recentă versiune a codului sursă este mereu disponibilă tuturor dezvoltatorilor, făcând astfel colaborarea și sincronizarea mult mai ușoară decât în cazul trimiterii de fișiere conținând cod sursă dezvoltatorilor interesați de proiect.

### Dicționar de termeni
* `git` - sistem de versionare
* `repository` - un „proiect” git ce conține toate fișierele și istoricul modificărilor
* `commit` - un set de modicări/adăugări/ștergeri a unui sau a mai multor fișiere din cadrul repository-ului

## Crearea contului GitHub
Primul pas este crearea unui cont [**GitHub**](https://github.com/), completând un username, adresa de email și o parolă. La următorul pas va trebui să selectați tipul de cont dorit. Implicit este selectat contul gratuit, care permite doar crearea de repository-uri publice. Apăsați „**Finish sign up**”.

Acesta este un moment bun pentru a valida adresa de email aleasă: tot ce trebuie să faceți este să accesați link-ul din interiorul email-ului primit de la GitHub.

## Crearea unui repository
Pagina de start a GitHub va conține acum rubrica ***GitHub Bootcamp***, o colecție de resurse suplimentare despre utilizarea GitHub. Noi ne vom axa pe crearea unui repository. Pentru aceasta dați click pe **+ New Repository**

{% include _utils/picture
    picture="/assets/images/tutorial/git/github-101/01-dashboard.png"
    title="GitHub homepage"
%}

Următorul pas este alegerea unui nume pentru repository. În câmpul „*Description*” puteți adăuga o scurtă descriere a proiectului. Nu uitați să bifați „**Initialize this repository with a README**”. Opțional puteți alege, în partea de jos a paginii, adăugarea unui fișier .gitignore și/sau a unei licențe.

Fișierul `.gitignore` este folosit de git pentru a ignora fișierele pe care nu le doriți în repository, de exemplu: fișiere generate la compilare, fișiere private, etc. Mai multe detalii puteți găsi aici: [help.github.com](https://help.github.com/articles/ignoring-files/).

Licența folosită determină condițiile în care o altă persoană poate folosi proiectul vostru. Un ghid alegerea unei licențe poate fi găsit aici: [choosealicense.com](http://choosealicense.com/).

{% include _utils/picture 
    picture="/assets/images/tutorial/git/github-101/02-new-repo.png"
    title="Crearea unui nou repository"
%}

După apăsarea butonului „**Create Repository**” veți ajunge pe pagina repository-ului nou creat.

{% include _utils/picture
    picture="/assets/images/tutorial/git/github-101/03-repo-created.png"
    title="Repository-ul a fost creat"
%}

## Instalarea și configurarea GitHub for Windows
În continuare vom descăra și instala aplicația GitHub for Windows de la adresa [windows.github.com](https://windows.github.com/). După instalare va trebui să vă autentificați în aplicație cu username-ul/adresa de mail și parola alese la crearea contului de GitHub.

{% include _utils/picture
    picture="/assets/images/tutorial/git/github-101/04-github-setup.png"
    title="Autentificare GitHub for Windows"
%}

În următorul pas va trebui să configurați identitatea voastră. Scrieți numele întreg și adresa de email. Acestea vor fi publice tuturor persoanelor care au acces la repository.

{% include _utils/picture
    picture="/assets/images/tutorial/git/github-101/05-github-setup-2.png"
    title="Configurarea GitHub for Windows"
%}

La ultimul pas puteți apăsa pe „**Skip**”, deoarece încă nu aveți niciun repository local.

{% include _utils/picture
    picture="/assets/images/tutorial/git/github-101/06-github-setup-3.png"
    title="Importarea repo"
%}

## Crearea primul commit
Acum vom clona (crea o copie locală) repository-ul creat anterior. Din aplicație vom da click pe „**+**”, vom selecta tab-ul „**Clone**”, contul și repository-ul pe care dorim să-l clonăm, iar în final vom apăsa „**Clone \<repo-name\>**”. Pe ecran va apărea o fereastră pentru selectarea directorului unde se va face clonarea.

{% include _utils/picture
    picture="/assets/images/tutorial/git/github-101/07-github-clone.png"
    title="Clonarea unui repository"
%}

Acum puteți adăuga fișierele sursă în folderul în care ați clonat repository-ul. În acest exemplu este vorba de fișierul *hello.c*.

{% include _utils/picture
    picture="/assets/images/tutorial/git/github-101/08-add-source-files.png"
    title="Adăugarea fișierelor sursă"
%}

Reveniniți în aplicația GitHub for Windows și selectați repository-ul. Veți observa pe coloana centrală că a detectat modificarea unor fișiere („*Uncommitted changes*”). Dați click pe Show pentru a vedea lista lor.

În coloana din dreapta vor apărea toate fișierele noi apărute în directorul repository-ului (ex: *hello.c*), precum și fișierele existente care au fost modificate de la ultimul commit (ex: *README.md*). Pentru a adăuga toate fișierele în repository bifați „*Files to commit*”. Dacă doriți un control mai fin asupra fișierelor puteți expanda fiecare fișier și selecta doar anumite linii. La final scrieți un mesaj de commit în câmpul Summary de pe coloana centrală și dați click pe commit.

{% include _utils/picture
    picture="/assets/images/tutorial/git/github-101/09-commit.png"
    title="Crearea unui commit"
%}

Ultimul pas este sincronizarea repository-ului local cu GitHub. Tot ce trebuie făcut este să dați click pe „**Sync**”.

**Important!** După fiecare commit este necesară sincronizarea cu GitHub pentru ca modificările să fie disponibile și online.

{% include _utils/picture
    picture="/assets/images/tutorial/git/github-101/10-push.png"
    title="Sincronizarea cu GitHub"
%}

Acum modificările create în ultimul commit vor fi vizibile tuturor persoanelor cu acces la repository.

{% include _utils/picture
    picture="/assets/images/tutorial/git/github-101/11-done.png"
    title="Done"
%}
