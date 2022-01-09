# Thesis as-a-webpage assignment

## Class structure

### Planning

| Class  | Activities|
| -------- | ---------------------|
| 31/01 (1) | (am) intro / presentations / writing exercice \| <br> (pm) notions: François (unpacking, boilerplate, sass), Thomas (CSS typography / calc), jekyll + markdown |
| ↓ | **Milestone:** You can distil your thesis to its *essence*, you have conceptual ideas of *potentialities*|
| 07/02 (2) | (am: 1h) 'mini-assignment' brief \| (rest: 7h) individual mentoring |
| ↓ | **Milestone:** You have ideas related to the structure, navigation, visual appearance and effects. <br> You started collecting references (*codepens, CSStricks, are.na, etc*) that could help you |
| 14/02 (3) | (am: 1h) 'mini-assignment' presentations (10ppl) (1/4) \| (rest: 7h) small group mentoring |
| ↓ | **Milestone:** You have design sketches and/or code sketches |
| 21/02 (4) | (am: 1h) 'mini-assignment' presentations (10ppl) (2/4) \| (rest: 7h) individual mentoring |
| ↓ &nbsp; **!!!!!!!** | **Milestone:** You've left the world of static design and are **coding/developing your webpage** |
| 28/02 (5) | (am: 1h) 'mini-assignment' presentations (10ppl) (3/4) \| (rest: 7h) small group mentoring |
| 07/03 (6) | (am: 1h) Group feedback / group troubleshooting \| (rest: 7h) individual mentoring |
| 14/03 (7) | (am: 1h) 'mini-assignment' presentations (10ppl) (4/4) \| (rest: 7h) individual mentoring |
| ↓ | **Milestone:** Your website is structurally sound, you are now adjusting elements more precisely |
| 21/03 (8) | (am: 1h) Group feedback / group troubleshooting \| (rest: 7h) individual mentoring |
| ↓ | **Milestone:** You are debugging / fine-tuning details across several screen sizes (mobile/desktop) |
| 28/03 (9) | (all day) help desk, *write your name* |
| 01/04 (Deadline) | **Your website is online (yay!)** |

### Mentoring days (7x)

#### Mentoring (individual) slots schedule, 1 on 1 (5x):

- 10:00  |  10:20 | 10:40 | 11:00 | 11:20 | 11:40
- 20 min break
- 12:20 | 12:40 | 13:00 | 13:20
- 60 min break
- 14:40 | 15:00 | 15:20 | 15:40 | 16:00
- 20 min break
- 17:00 | 17:20 | 17:40 | 18:00

#### Mentoring (small groups) (4-5 per group) (2x):

- 10:00 | 11:00
- 20 min break
- 12:20 | 13:20
- 60 min lunch break
- 15:20 | 16:20
- 20 min break
- 17:40

## Main assignement

- Conceptualize, design, and implement a content-based website &ndash; a publication &ndash; your kabk thesis.
- Deploy it on the kabk Github.

Criterias...

- Your website is accessible / is legible
- Your website works on mobile, is actually mobile-first (you've started your design process with mobile screens in mind).
- Your website loads 

## Mini/bonus assignment

- present a website of your choice in 4 min (*1/2 pecha kucha*, 10 slides of 20sec) x 10 students per session (1h)

## First class

### A.M. (ante meridiem)

- Intro (this document)
- Round table presentation
- Setting up of a common Etherpad ->
- Individual writing exercice + presentation
- (dividing the group into sub-groups (4-5 students) based on their thesis subjects / writing styles / interests / possible media treatments (text-based, media-based, etc). Presentation of text-ideas / general concept?)

### P.M. (post meridiem)

Presentation of web notions / workshop...

1. François unpacks focus points of a web page (in 2022), talks about document structure / boilerplate, and gets into SASS (Syntactically Awesome Style Sheets)
2. Thomas delves into CSS functions (https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Functions), variables, calcs, rems, etc.
3. Jekyll + Markdown, work with footnotes
4. (how to) deploy on Github Pages

### Github pages

Documentation: https://pages.github.com

Ways of connecting / using:
- Terminal: either Git ([documentation](https://git-scm.com/download/mac)),or the Github CLI ([documentation](https://github.com/cli/cli)) *
- Desktop app: Github Desktop**, ([Download here](https://desktop.github.com))

\* CLI = Command User Interface, ** GUI = Graphic User Interface

#### I. Git (or Github CLI)

1. Be sure you have Homebrew (a package manager) installed on your computer (if Mac / Linux). (https://brew.sh) To install, type this in 'Terminal':

```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

2. Then, install Git (https://git-scm.com/download/mac) by typing in 'Terminal': `brew install git`, or if installed update it with `brew upgrade git`. (Github CLI can be installed by typing `brew install gh`) ()

- You might need to update Xcode to 11.3.1 (if Mac)... if an error asks for Xcode update, download here: https://xcodereleases.com
- You might need to make sure your github account has authentification tokens enabled: https://stackoverflow.com/questions/68775869/support-for-password-authentication-was-removed-please-use-a-personal-access-to

#### II. Desktop app

[Download here](https://desktop.github.com), and follow the installation steps.
