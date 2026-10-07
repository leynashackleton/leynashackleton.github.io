# Editable CV

The source extracted from `../resume.zip` is maintained here. The original archive
is preserved. The current public PDF is `../pdfs/leynaShackletonCV.pdf`.
The historical main-source filename does not change the display name, Leyna Shackleton.

Build from this directory with an installed TeX distribution:

```sh
latexmk -pdf -interaction=nonstopmode -halt-on-error -outdir=../tmp/pdfs/build henryShackletonCV.tex
cp ../tmp/pdfs/build/henryShackletonCV.pdf ../pdfs/leynaShackletonCV.pdf
```

The native Codex LaTeX editor also confirmed successful compilation of the source.

## 2026-10-01 [codex] bibliography and rendering repair

Scope: supplied archive and bibliography records checked as of 2026-10-01.
Fixed the missing comma in the dissipative-spin-liquid entry, enabled preprints,
added the January 2026 Dirac spin-liquid preprint, updated the coding preprint
title, and ordered 2026 publications by publication date. Preprint years retain
the first-submission year. Protected the XDiag capitalization. Repaired wrapped
DOI links and changed DOI/arXiv links to HTTPS. Kept bibliography entries,
posters, and teaching content together across page breaks. Synchronized the two
outdated bibliography records in `../cv.md`.

Evidence inspected: [Dirac spin liquids](https://arxiv.org/abs/2601.19980),
[coding preprint v2](https://arxiv.org/abs/2503.15483),
[polaronic preprint v2](https://arxiv.org/abs/2408.02190),
[twisted quantum doubles](https://doi.org/10.1103/j6h1-hzyz),
[XDiag](https://arxiv.org/abs/2505.02901),
[chiral superconductor](https://arxiv.org/abs/2509.21591), and
[triangular antiferromagnets](https://arxiv.org/abs/2311.01572).
No journal reference was present in the three preprint records inspected.

Validation: successful latexmk/BibTeX build; successful native editor compilation;
all four final page images visually inspected, with no clipping or overlap;
15 published entries and three preprints checked in generated bibliographies;
all 15 distinct DOI links and all arXiv annotations checked for HTTPS and whitespace.
Only the moderncv icon fallback and a visually harmless title underfull-box warning remain.

Base revision: `4f0e8a8c40c19a58b03a412ab83b209bd9f0c11f`. Changes remain uncommitted and unpublished;
unrelated README/AGENTS changes were preserved. No scheduler or remote project applies.
Original archive SHA-256: `d8730b88ad84b5f43201424a8764902e1c44f86dc5e87026d4315e252b96dd3d`.
Final PDF SHA-256: `557b96577594c6af30e6c5487e3ec409d6ffd8cb09f8f6b8fd2b3cc537ec2b0c`.

Open issue / next action: a full talks/posters update is outside this repair.
The archive has different dates and fewer presentations than `cv.md`; verify
those shared records against event programs before synchronizing them.

## 2026-10-01 [codex] cleanup

Removed the redundant `resume-updated.zip` export after verifying every archived
file against the retained source and public PDF. The original supplied archive
and current CV were preserved. Added scoped ignore rules for future CV build
output. PDF checksum is unchanged; no recompilation was needed. Changes remain
uncommitted and unpublished. Next step remains the talks/posters verification above.

## 2026-10-01 [codex] presentation maintenance

Scope: targeted presentation review, September 2025 through October 2026,
including the confirmed October 20 NYU seminar. Older website talks were
reconciled with the PDF CV; this was not a full historical or poster audit.
Added KITP and two Minnesota talks, the upcoming NYU seminar, and six slide PDFs
(KITP, Minnesota seminar/colloquium, Nordita, Pappalardo, Rutgers). Corrected the
MIT and Harvard Kids talks to September 2025 as confirmed by the user. Used the
user-confirmed Minnesota seminar date/title, September 25 and “Anyonic neural
quantum states”; the supplied slide cover retains its earlier preparation date.
Used the user-selected KITP program title, “Neural-Network Variational Monte
Carlo for Anyons.” Restored four 2024 talks omitted from the imported PDF CV,
using the website's month-level dates, and added all existing slide links to
that CV. Preserved the completed bibliography repair.

Public evidence inspected: [KITP program](https://online.kitp.ucsb.edu/online/aiqmatter-c26/),
[NYU seminars](https://physics.nyu.edu/events.html?EventsPage=cqp),
[Nordita timetable](https://indico.fysik.su.se/event/9148/timetable/?print=1&view=standard_inline_minutes),
[MIT Pappalardo symposium](https://physics.mit.edu/research/pappalardo-fellowships-in-physics/pappalardo-symposium/),
[Rutgers conference](https://cmsr.rutgers.edu/newsevents-cmsr/event-details/1370-130th-statistical-mechanics-conference),
[APS abstract](https://meetings-archive.aps.org/smt/2026/mar-m45/8/), and
[NUS seminars](https://sites.google.com/view/nuscmseminars/home/upcoming-previous).
Relevant correspondence and supplied title pages supplemented those records;
private correspondence is not retained in this repository.

Slide exports: retained supplied PDFs for four events. Used local PowerPoint
printing exports for Pappalardo and Minnesota seminar, with notes excluded.
Removed the Pappalardo chat screenshot at the user's direction and flattened
its final animation states to avoid overlapping objects. Restored two Minnesota
EMF diagrams from the corresponding supplied figure PDFs to fix export loss.
Supplied originals were preserved; videos/animations become static PDF content.

Validation: successful documented latexmk/BibTeX and Franklin builds; five CV
pages visually inspected, with presentation pages rechecked after the final
correction; slide decks rendered and scanned, with repaired pages inspected at
full size; website presentation layout inspected in Chrome. All 29 presentation
records and 23 slide links agree between the website and PDF CV, and every
local slide target exists. No private staging directory, archive, editable CV
source or guidelines were copied into the generated site. Optional website
minification was unavailable locally; the build completed successfully.

Base revision: `4f0e8a8c40c19a58b03a412ab83b209bd9f0c11f`, local `main`;
existing CV repair and website-guideline changes are retained in this maintenance
commit. No remote scientific project or scheduler applies. Publication is via
the authorized push to `main`, the existing Franklin workflow, and `gh-pages`;
live deployment verification follows the push.
Final CV SHA-256: `81141187b39741abbbb9c297a375eca6bdd13fe6a8fd6f6b07accaff3dbfb8e6`.

Open issue / next action: posters remain outside this presentation pass. At the
next poster update, verify the stale June 2026 upcoming entry and reconcile the
Ultra-Quantum Matter date and poster coverage between the two CV versions.

Deployment follow-up: the first successful workflow carried forward the tracked
CV HTML instead of regenerating it, although it copied the new slide assets.
Changed the Franklin deployment call to `optimize(clear=true)` so each publish
regenerates the output from source. The local clean build regenerated the final
CV page and excluded private working files; live checks follow the corrected
deployment.

The clean rebuild alone did not resolve publication. Inspection of the deploy
action log identified its forced checkout of the source revision, which resets
tracked `__site` files after the build. The workflow now preserves the generated
website in an ignored `.deploy-site` directory before invoking that action.
The staging directory is also excluded from Franklin inputs. A bounded Git
fixture reproduced the overwrite and confirmed that the untracked snapshot
survives it. The supplied assets and editable sources remain unchanged.

Publication verified on 2026-10-01: content commit `7df265d690354beb4b77a08715b6b8cd1de7b905`
and deployment fixes through `345654229a` are published. Franklin workflow
[36911909776](https://github.com/hshackle/hshackle.github.io/actions/runs/36911909776)
and Pages deployment
[36912148173](https://github.com/hshackle/hshackle.github.io/actions/runs/36912148173)
both completed successfully, with `gh-pages` at `f25364e73c`.
The [live CV](https://hshackle.github.io/cv/) shows the final presentation records
and 23 working slide URLs (HTTP 200). All six new slide PDFs and the CV download
match their local SHA-256 checksums; the published presentation page was also
visually inspected. The source checkout was clean before adding this handoff
note; temporary slide exports and QA images were removed, while the supplied
originals and preserved import remain local. This documentation-only follow-up
is excluded from the website and does not require another deployment.
Next action remains the poster reconciliation described above.

## 2026-10-01 [codex] presentation label polish

Scope: wording of the existing presentation list, 2018 through October 2026.
Standardized 16 seminar/event labels in both CV sources with title capitalization
and event-before-institution ordering. Expanded the Harvard label to
“Condensed Matter Theory Kids' Seminar, Harvard University,” matching the
[Tufts-published Boston Area Physics Calendar](https://cosmos.phy.tufts.edu/mhonarc/bapc/msg01475.html).
Research titles, dates, presentation types, and all 23 slide links are preserved.
This was a formatting pass, not a new factual audit.

Validation: documented latexmk/BibTeX and clean Franklin builds succeeded; both
presentation PDF pages and the website preview were visually inspected.
Compared research titles/dates to the prior source revision and verified that
all 23 slide links agree between sources and resolve locally.
Base revision: `94f27f3`, initially clean local `main`. Generated tracked output
is restored after preview because the deployment workflow regenerates it.
The authorized push publishes the two CV sources and rebuilt public PDF;
live deployment verification follows.
CV SHA-256: `212e45c62154590cd39c1f14875439a121e0939b3dabdc1d963ec830527ea284`.
Next action remains the poster reconciliation recorded above.

Publication verified: `8c87aa98` is published. Franklin
[36942341678](https://github.com/hshackle/hshackle.github.io/actions/runs/36942341678)
and Pages
[36942517228](https://github.com/hshackle/hshackle.github.io/actions/runs/36942517228)
completed successfully. The live presentation page shows the revised labels
and was visually inspected; the downloaded CV matches the checksum above.
The working tree was clean before this documentation-only handoff note.


## 2026-10-01 [codex] website address migration

Scope: migrate the existing website and CV to
[leynashackleton.github.io](https://leynashackleton.github.io/) following the
user's GitHub account rename. Public repository metadata confirmed ownership
under `leynashackleton`; the repository rename to `leynashackleton.github.io`
was still pending at the initial check. Updated the project title, Franklin
website URL (previously the upstream template address), and all 24 local-site
links in the editable CV. Rebuilt the public CV with the documented
latexmk/BibTeX workflow; retained historical source filenames and past
maintenance evidence links. No new content audit was performed.

Validation: successful five-page CV build and clean Franklin build; all PDF
pages and website CV preview visually inspected. Extracted CV text agrees
with the prior PDF except for the homepage address. Verified the homepage
link plus all 23 slide URLs and their existing local assets; feed and sitemap
use the new hostname. Optional website minification was unavailable locally.
Generated tracked website output was restored after preview because CI
regenerates it. Base revision: `f9cf8a873f8004cdc7f040c4d9fddcb1e6abe8cb`,
initially clean local `main`; the source/PDF/documentation changes comprise
this migration. No scientific remote project or scheduler applies.
CV SHA-256: `93e7ae806c75c793a7d1e3068d1fffb88d0258f9144dc1cf2779f242a0a10837`.

Publication verified on 2026-10-01: migration commit
`3267188f834dc2ff82056aa0a67eb6686a6cd40b` is published at the exact renamed
repository `leynashackleton/leynashackleton.github.io`; local origin now points
to it. Franklin workflow
[36944087787](https://github.com/leynashackleton/leynashackleton.github.io/actions/runs/36944087787)
and Pages deployment
[36944265944](https://github.com/leynashackleton/leynashackleton.github.io/actions/runs/36944265944)
completed successfully, with published `gh-pages` revision
`d8ad8939785e71c27a9e8c91998c99d46b046e66`. Home, Research, and CV pages and all
23 slide URLs return HTTP 200. The live CV download matches the SHA-256 above;
feed and sitemap use the new hostname. The live homepage was visually
inspected. The source checkout was clean before this documentation-only
handoff update, which is excluded from website inputs and skips deployment.

The former `hshackle.github.io` homepage returns HTTP 404, with no redirect.
Next action: update external profile links and bookmarks to the new address;
preserving the former hostname would require separate account/site setup.
The previously recorded poster-reconciliation work remains outside this pass.

## 2026-10-07 [codex] SciPost Physics acceptance

Scope: status of the Unifying Dirac Spin Liquids paper, arXiv:2601.19980.
Authority: the user's direct confirmation of acceptance in SciPost Physics on
2026-10-07. The [arXiv record](https://arxiv.org/abs/2601.19980) confirms the
existing title and author order; it has no final journal citation. The public
SciPost submission page was inaccessible during this check. No volume, article
number, journal DOI, or acceptance date was inferred.

Moved the existing bibliography entry from preprints to publications, with
SciPost Physics as the journal and an explicit accepted-for-publication note.
Updated the website entry while retaining its arXiv link. Documented latexmk/
BibTeX and clean Franklin builds passed; native editor compilation also passed.
All five PDF pages and the website publication entry were visually inspected;
checked 16 published/accepted entries, two preprints, no duplicate paper entry,
and unchanged presentation/poster/teaching pages. Optional website minification
is unavailable; the build completed successfully.

Base revision: `fd402072baf88e5ea02c200ca89d11106d2f17cc`, initially clean local
`main` and synchronized with origin. Generated preview files will be restored
or removed; source, bibliography, PDF, and this note constitute the update.
Publication is via the authorized main-branch push and existing Franklin/Pages
workflows; deployment and live-PDF verification follow the push.
CV SHA-256: `bfd6641e092b0fdf0937fbb82d8e1f33f7d80e1bb021c2e79fbc316367fdf5ae`.
Next action: replace the acceptance note with the final journal citation when
available. The previously recorded poster reconciliation remains outside scope.

Publication verified on 2026-10-07: content commit `dc07bfd9c5f78fb392bba3b11a50b838ab813f57`
is live. Franklin [37659183666](https://github.com/leynashackleton/leynashackleton.github.io/actions/runs/37659183666)
and Pages [37659427607](https://github.com/leynashackleton/leynashackleton.github.io/actions/runs/37659427607)
both succeeded, with `gh-pages` at `5f6218996ae0177e43113f433fdd6892a8f4ef11`.
The [live CV page](https://leynashackleton.github.io/cv/) returns HTTP 200 and
shows the acceptance; its publication entry was visually inspected in Chrome.
The public PDF returns HTTP 200 and exactly matches the checked local PDF
and checksum above. The source checkout was clean before this documentation-only
verification note. No factual questions remain for this acceptance update.
