---
layout: layouts/post.njk
title: About
templateClass: tmpl-post
eleventyNavigation:
  key: About 
  order: 3
---
# Why do this?

Free access for the public to published judgments from the Singapore Courts is uneven and spread out across several sources. For instance, while Supreme Court (Court of Appeal + High Court) judgments are available on the [Judiciary's website](https://www.judiciary.gov.sg/judgments/judgments-case-summaries), State Court (Magistrate + District Courts) are only available on [CommonLII](http://www.commonlii.org/sg/) (Cases from 2006 onwards) or via [LawNet's free resources feed](https://www.lawnet.sg/lawnet/web/lawnet/free-resources) (which gives you the past 3 months' worth of judgments).

This is an attempt to answer the questions of: 
- What does it take to deliver better public access to judgments?
- How do we deal with searching and presenting huge corpuses of unstructured text? 

# Where judgments are sourced from
Judgments are sourced from the [OpenDoc State Court judgments repository](https://github.com/opendocsg/opendoc-state-court-judgments/).

# TODO 
## File organisation / naming 
- [x] Write script to combine index.md and report.md into one file for ease of linking content. Each judgment has a folder in OpenDoc's repo, and contains 2 files: index.md and report.md. index.md appears to contain the front matter for the judgment (e.g. tags, title etc) while report.md contains the judgment.
- [x] Automate process of renaming files from report.md to its citation e.g. 2022_SGDC_272 so that URLs refer to each unique judgment e.g. localhost:8080/2022_SGDC_272/
- [ ] Front matter:
  - [ ] Maybe add level of court to the file's front matter based on file name??
  - [ ] Add date (parse subtitle since dates are contained in it)


## Updating the site 
- [ ] (If the OpenDoc repo is reformatted to use one file per judgment): Add opendoc's repo as a submodule, then generate files from that so that I don't have to deal with storing my own files. Can maybe use GH actions to regenerate the site when the OpenDoc repo gets updated??  
- [ ] Crawler stuff
  - [ ] Maybe fork the OpenDoc State Courts crawler and modify it to have front matter + report combined in the same file so I don't have to do everything in the File Org/Naming section ever again
  - [ ] Use Github Actions instead of Travis?? idk
- [ ] Add search functionality. Potential candidates: Docsearch by Algolia; Typesense (need to self-host though); Elasticlunr?


## Misc
- [ ] Figure out how build time will scale w. judgments and to also figure out roughly how many judgments are published per year
- [ ] Add graphic with info about the different courts/tribunals in SG 
- [ ] Nicer styling for judgments :P 