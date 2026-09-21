# Security policy

This policy covers every public repository owned by [mixutin](https://github.com/mixutin) that
does not have a `SECURITY.md` of its own. If a repository has its own policy, that one applies
instead.

🇫🇮 [Suomeksi alempana](#suomeksi)

## How to report a vulnerability

Please report security problems privately. Do not put details in a public issue, discussion or
pull request.

1. **Use private vulnerability reporting.** Open the repository on GitHub, go to its
   **Security** tab and choose **Report a vulnerability**. Only you and the maintainer can see the
   report, and we can talk it through there.
2. **If a repository has no "Report a vulnerability" button**, open a short public issue that
   asks for a private channel and nothing else, for example: *"I'd like to report a security
   issue. Could you enable private vulnerability reporting?"* Do not include the affected file,
   the kind of bug, or any proof of concept. I will reply with a way to send the details
   privately.

## What to include

- The repository, and the branch, commit or release you tested.
- What the problem is, and what an attacker could do with it.
- Steps to reproduce it, or a minimal proof of concept.
- Anything the attack depends on: configuration, network position, an account, local access.
- Whether anyone else knows about it, and whether you plan to publish.
- How you would like to be credited: your handle, or anonymous.

Please redact real keys, tokens, passwords and other people's data. If you had to see such data
to find the problem, say so, but do not send it.

## What to expect

These are hobby projects, maintained by one person in spare time. Everything below is best
effort, not a guarantee.

- I try to acknowledge a report within a week, and to give a first assessment within a month.
- I will keep you updated while I work on a fix, and ask you to check it if you are willing.
- When a fix is out, I will publish a GitHub security advisory and credit you, unless you prefer
  to stay anonymous.
- There is no bug bounty. I cannot pay for reports.

If you have not heard back within two weeks, a short follow-up on the same report is welcome.

## Coordinated disclosure

Please give me a reasonable chance to fix the problem before you talk about it in public. The
default is **90 days** from your report, or the day a fix is released, whichever comes first.
If a problem is being actively exploited, or a fix needs longer, we can agree on a different
date. I will not ask you to stay quiet forever.

## Safe harbor

If you research and report in good faith under this policy, I consider your research authorized,
I will not take or support legal action against you for it, and I will work with you to
understand and fix the problem. Good faith means:

- You test only against **your own installation** of the software. Do not test against servers,
  PCs or accounts run by other people, including mine and my friends', without their permission.
- You do not access, change or delete data that is not yours. If you come across someone else's
  data by accident, stop, and tell me in your report.
- You do not degrade service for others: no denial of service, spam or brute forcing against
  live systems.
- You do not use social engineering, phishing or physical attacks.
- You give me reasonable time before disclosure, as described above.

This safe harbor covers only my own projects. I cannot authorize testing of anyone else's
systems or services.

## Out of scope

- **Third-party games and their original online services.** Some of my projects work with games
  made by other companies, or with servers those companies used to run. Problems in the game
  clients themselves, or in the original services, are not mine to fix. If the company still
  exists, report to them.
- **Upstream projects.** When a repository is a fork of, or depends on, someone else's project,
  report problems in the original code to that project. If the problem is in a change I made,
  report it here.
- **Third-party services**, such as GitHub, GitHub Pages or a VPN provider. Report to the
  service.
- Attacks that need an already compromised machine, or physical access to it.
- Running software against its documentation, for example exposing a service that the setup
  guide says must stay private.
- Findings from automated scanners with no demonstrated impact, and missing best-practice
  headers or settings with no practical attack.
- Requests for cheats, game files or help with piracy. These are not security reports.

---

## Suomeksi

Tämä ohje koskee kaikkia mixutinin julkisia projekteja, joilla ei ole omaa tietoturvaohjetta.

**Mikä on haavoittuvuus?** Se on tietoturva-aukko: virhe, jonka avulla joku voisi päästä käsiksi
tietoihin tai laitteisiin, joihin hänellä ei ole lupaa.

### Näin ilmoitat

- Ilmoita aina yksityisesti. Älä kirjoita yksityiskohtia julkiseen keskusteluun.
- Avaa projekti GitHubissa, mene **Security**-välilehdelle ja valitse **Report a vulnerability**.
  Silloin vain sinä ja ylläpitäjä näette ilmoituksen.
- Jos painiketta ei ole, avaa lyhyt julkinen issue (tehtävä tai kysymys projektin sivulla) ja pyydä
  siinä vain yksityistä yhteystapaa. Älä kerro siinä itse ongelmasta mitään.

### Mitä ilmoitukseen kannattaa kirjoittaa

- Mitä projektia ja mitä versiota ongelma koskee.
- Mikä ongelma on ja mitä sillä voisi tehdä.
- Miten ongelman saa toistettua.
- Miten haluat, että sinut mainitaan: nimimerkillä vai nimettömänä.

Älä lähetä oikeita salasanoja, avaimia tai muiden ihmisten tietoja.

### Mitä sen jälkeen tapahtuu

Nämä ovat harrastusprojekteja, joita teen vapaa-ajallani yksin. Yritän vastata viikon sisällä,
mutta aina se ei onnistu. Palkkioita en pysty maksamaan. Kun korjaus on valmis, julkaisen siitä
tiedotteen ja kiitän ilmoittajaa, jos hän niin haluaa.

Anna minulle aikaa korjata ongelma ennen kuin kerrot siitä julkisesti. Tavallisesti aikaa on
90 päivää, tai vähemmän, jos korjaus valmistuu sitä ennen.

### Turvasatama

Jos toimit hyvässä uskossa ja noudatat tätä ohjetta, en ryhdy oikeustoimiin sinua vastaan.
Testaa vain omaa asennustasi, älä muiden ihmisten palvelimia tai koneita. Älä koske muiden
tietoihin äläkä häiritse muiden käyttöä.

### Mitä tämä ohje ei koske

- Muiden yritysten pelejä ja niiden alkuperäisiä verkkopalveluja.
- Alkuperäisiä projekteja, joihin omat projektini perustuvat. Ilmoita niiden virheistä suoraan
  niiden tekijöille.
- Muita palveluja, kuten GitHubia.
- Huijausohjelmia, pelitiedostoja tai piratismia koskevia pyyntöjä.
