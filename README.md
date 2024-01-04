This is the web site of the XAI group in Marburg.  This website is based on the minimal-mistakes jekyll theme. 

# Editors
> :warning: **Make sure you are on the `main`-branch**

![warning-img](img/main-branch.JPG)
> :information_desk_person: what you see in the online preview is likely not what you get

> :zzz: changes will take a few mins to take effect. Monitor progress at [actions tab](https://github.com/IKIM-Essen/ikim-website/actions)

## Howto...
- [manage team members](#member)
- [manage publications](#publications)
- [add a project](#project)
- [add a new group](#new)
- [edit pages](#edit)



<h3 id="member">Manage Team members</h3>

Members of a group are defined in [`/_data/people.yml`](/_data/people.yml).

Example entry:
```
- name: Hilde Muster
  mail: hilde.muster@example.org
  roles: ['shk']
  img: Muster-Hilde.jpg
```
#### Add Member
Add a new entry to the end of the file. See the example above or existing entries for proper format.  

Mandatory fields:
- name - first and last name
- roles - must be a list, even if it only has a single entry. The first entry **must** be the position in the group. Possible values:
  * shk - student assistant
  * phd - PhD candidate
  * phd - external PhD candidate
  * postdoc - Researcher
  * admin - Administration
  * tech - Technical staff
  * head - group leader  
  Additional entries in the roles-list are optional

Optional fields:
- mail - e-mail address, e.g. `hilde.muster@example.org.` Multiple e-mail addresses are possible, must be provided as list, e.g., `['mail1@example.org', 'mail2@example.org']`
- phone - phone nr, e.g. `+4920112345`
- title - e.g. `Prof. Dr.`
- position-special - more details for tech-staff, e.g. `HPC specialist`
- interests - a list of interests, e.g. `['machine learning', 'coffe']`
- img - first, upload an image to [`/img/people`](/img/people), then provide the filename here, e.g. `Muster-Hilde.jpg`

#### Remove Member
Simply delete the corresponding entry from the file.

#### Modify Member
Edit the entry as needed.

<h3 id="publications">Manage Publications</h3>

Replace `references.bib` at [`/_bibliography`](/_bibliography) with your latest bibtex list of publications.

Make sure that exclusively either `doi` or `url` are set for an entry (not both). If both are available, `doi` is to prefer. You may use the export options of your favorite reference manager to remove the unnecessary one, e.g. [Zotero](https://www.zotero.org) with [Better Bibtex](https://retorque.re/zotero-better-bibtex/).

# Devs
The site is built with [jekyll](https://jekyllrb.com), [scholar](https://github.com/inukshuk/jekyll-scholar)-plugin and [minimal mistakes](https://mmistakes.github.io/minimal-mistakes/) theme.
## Run locally
1. Install [Ruby](https://www.ruby-lang.org)
2. Install [Bundler](https://bundler.io) `gem install bundler`
3. Checkout repo, install dependencies in the repo with `bundle install`
4. Run with `bundle exec jekyll serve`, the site is accessible at "http://127.0.0.1:4000/" (note the trailing `/`)

## Theme customization
`/assets/main.scss` loads the main theme configuration and holds custom adaptations.

## Todo
- [ ] bib: add publication for team members -> link to bibliography with that filter
- [ ] bib: add author version PDF support (kind of vanished from ikim example ..) 
- [ ] bib: limit number of authors per bibentry (10? SIGIR forum paper is quite long)
- [ ] bib: add support to remove item numbers in bibliography (cf. blog post about Meike's cvpr paper)
- [ ] update images for all team members
- [ ] change default font to roboto (Apache Licence Google Font, need to install it)
- [ ] news: Paper Paul
- [ ] news: Paper Osman
- [ ] news: Paper Bach
- [ ] news: SIGIR forum article


