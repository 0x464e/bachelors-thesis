# Bachelor's Thesis
## Choosing a Performance Testing Tool for Web Services
## Suorituskyvyntestaustyökalun Valinta Web-Sovelluspalveluiden Testaamiseen

This repository hosts my bachelor's thesis, which was on the topic of choosing a performance testing tool for web services. The thesis answers questions:

1. How to choose the correct performance testing tool for testing web services?
2. What factors should be taken into consideration when comparing different tools?

The thesis is written in Finnish using LaTeX.  
[This](https://github.com/villekol/tau-latex-thesis-template) awesome LaTeX thesis template for Tampere University was used in this project.

## Abstract
You can find the abstract of this thesis in both Finnish and English under these spoilers.  
Click them to expand the four paragraphs. 

<details>
  <summary>English</summary>
  Performance testing tools are test automation tools that can be used to test the performance of a system. There are many different types of performance testing tools, and you need to know how to choose the right one for your needs. There are many different types of software that need performance testing. For this reason, the scope of this work is limited to performance testing of web services. How to choose the right performance testing tool for testing web services? What factors should be considered when comparing different tools?

  Web services are software systems that enable computers to interact with one another. In other words, they are a very central part of modern world IT infrastructure. For this reason, their proper functioning is sought after through software testing, of which performance testing is an important step. Performance is a measure of a program's ability to operate quickly over time and its ability to use available resources efficiently. Performance is tested using specialized performance testing tools.

  The work was carried out as a literature review, so the material used was obtained by performing searches on various search services. The searches can be divided into two categories. The first category includes searches that directly addressed the research questions of this thesis. The second category includes searches to justify the background information for the work, or the importance of factors related to the selection of the performance testing tools. The literature review favored scientific sources and tried to find scientific justifications rather than opinions.

  The results of this work consist of a discussion of the selection factors found through the literature review. For the sake of clarity, the different selection factors are divided into two categories, organizational factors, and tool-specific factors. These two categories are each further subdivided into three subcategories to be discussed separately. The organizational factors address the financial cost of performance testing tools, the magnitude of the need for use and the available support. The tool-specific factors deal with the type of testing required, compatibility and usability. The above selection factors found in scientific sources will be compared with personal opinions or guides of professionals found on the internet. This comparison shows that the results of this work are comprehensive and cover a wide range of factors related to the selection of performance testing tools.

</details>

<details>
  <summary>Finnish</summary>
  Suorituskyvyntestaustyökalut (engl. performance testing tool) ovat testiautomaatioon liittyviä työkaluja, joilla voidaan testata järjestelmän suorituskykyä. Suorituskyvyntestaustyökaluja on monia erilaisia ja niistä pitää osata valita oikea omiin tarpeisiin. Erilaisia ohjelmistoja, joilla on tarvetta suorituskyvyntestaukseen, on erittäin monia. Tästä syytä tämän työn aihe on rajattu web-sovelluspalveluiden suorituskyvyntestaamiseen. Miten valitaan oikea suorituskyvyntestaustyökalu web-sovelluspalveluiden testaamiseen? Mitä tekijöitä pitää ottaa huomioon, kun vertaillaan eri työkaluja?


  Web-sovelluspalvelut (engl. web service) ovat ohjelmistojärjestelmiä, jotka mahdollistavat tietokoneiden keskeisen vuorovaikutuksen. Toisien sanottuna ne ovat hyvin keskeinen osa nykymaailman IT-infrastruktuuria. Tästä syystä niiden moitteettomaan toimimiseen pyritään ohjelmistotestauksella, jonka yksi tärkeä vaihe on suorituskyvyntestaus. Suorituskyky kertoo ohjelman kyvystä toimia nopeasti ajan suhteen ja sen kyvystä käyttää saatavilla olevia resursseja tehokkaasti. Suorituskykyä testataan erikoistuneilla suorituskyvyntestaustyökaluilla.


  Työ suoritettiin kirjallisuuskatsauksena, joten käytettävä aineisto saatiin suorittamalla hakuja eri hakupalveluilla. Tehdyt tiedonhaut voidaan jakaa kahteen kategoriaan. Ensimmäiseen kategoriaan kuuluu haut, joilla etsittiin suoraan vastauksia tämän työn tutkimuskysymyksiin. Toinen kategoria sisältää haut, joilla perusteltiin työn taustatietoja, tai löydettyjen suorituskyvyntestaustyökalujen valintaan liittyvien tekijöiden tärkeyttä. Kirjallisuuskatsauksessa suosittiin tieteellisiä lähteitä ja pyrittiin löytämään mielipiteiden sijaan tieteellisiä perusteluja.


  Työn tulokset muodostuvat kirjallisuuskatsauksen avulla löydettyjen valintatekijöiden käsittelystä. Eri valintatekijät jaetaan selkeyden vuoksi kahteen kategoriaan, organisatorisiin tekijöihin ja työkalukohtaisiin tekijöihin. Nämä kaksi kategoriaa jaetaan molemmat vielä kolmeen erikseen käsiteltävään alakategoriaan. Organisatorisissa tekijöissä käsitellään suorituskyvyntestaustyökalujen rahallisia kustannuksia, käyttötarpeen suuruutta ja saatavilla olevaa tukea. Työkalukohtaisissa tekijöissä perehdytään tarvittavaan testaustyyppiin, yhteensopivuuteen ja käytettävyyteen. Edellä mainittuja tieteellisistä lähteistä löydettyjä valintatekijöitä vertaillaan internetistä löytyviin alan ammattilaisten henkilökohtaisiin mielipiteisiin tai oppaisiin. Vertailun perusteella saadaan selville, että tämän työn tulokset ovat kattavat ja käsittelevät suorituskyvyntestaustyökalujen valintaan liittyviä tekijöitä laajasti.
</details>

You can find the full thesis as a pdf file [from the pdf folder](pdf/thesis.pdf).

### Compilation

This template uses `biblatex`, `glossaries` and `svg` packages, and therefore needs a non-standard compilation sequence. `--shell-escape` is needed to launch InkScape for svg conversion. InkScape needs to be found in PATH.

```
pdflatex --shell-escape main.tex
makeindex -s main.ist -t main.glg -o main.gls main.glo
biber main
pdflatex main.tex
pdflatex main.tex
```

If imported to Overleaf, it works just fine there as well.  
I uploaded a copy to Overleaf here:  
https://www.overleaf.com/read/zdjzwbbnjcxn

## GitHub Actions
This project contains two GitHub Actions workflows.  
* [`overleaf-sync.yml`](.github/workflows/overleaf-sync.yml) syncs changes from Overleaf to GitHub every 15 minutes. [Overleaf Sync with Git](https://github.com/subhamx/overleaf_sync_with_git) is used as a free alternative to achieve this instead of paying Overleaf for this feature.
* [`clear-artifacts.yml`](.github/workflows/clear-artifacts.yml) is used to clear artifacts as needed. The very frequently running Overleaf sync workflow could fill your storage quota, so this workflow could delete old useless artifacts that take up space.

## Length
The length of this thesis is just about 5000 words in 20 pages.  
Word count is calculated according to official Tampere University word counting rules.