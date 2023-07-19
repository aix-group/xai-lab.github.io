This is the web site AI group in Marburg. AI-MR. 

This website is based on the minimal-mistakes jekyll theme. 

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
Simply delete the corresponding entry from the file

#### Modify Member
Edit the entry as needed



<h3 id="publications">Manage Publications</h3>

Replace `references.bib` at [`/_bibliography`](/_bibliography) with your latest bibtex list of publications.

Make sure that exclusively either `doi` or `url` are set for an entry (not both). If both are available, `doi` is to prefer. You may use the export options of your favorite reference manager to remove the unnecessary one, e.g. [Zotero](https://www.zotero.org) with [Better Bibtex](https://retorque.re/zotero-better-bibtex/).

# Devs
The site is built with [jekyll](https://jekyllrb.com), [scholar](https://github.com/inukshuk/jekyll-scholar)-plugin and [minima](https://github.com/jekyll/minima) theme.
## Run locally
1. Install [Ruby](https://www.ruby-lang.org)
2. Install [Bundler](https://bundler.io) `gem install bundler`
3. Checkout repo, install dependencies in the repo with `bundle install`
4. Run with `bundle exec jekyll serve`, the site is accessible at "http://127.0.0.1:4000/" (note the trailing `/`)

## Deployment
Github-pages does not support the scholar plugin. Hence, the site is first built via a github action at `/.github/workflows/build.yml` from the main branch. This action then pushes the ready-to-deploy build artefact to the gh-pages branch for deployment.

## Theme customization
`/assets/main.scss` loads the minima theme and customization in `/_sass/_ikim.scss`

## Todo
- [ ] add author version PDF support
- [ ] improve color scheme
- [ ] add publication for team members -> link to biliography with that filter
- [ ] update images for all team members
- [ ] add propper logo
- [ ] add favicon
- [ ] check and adapt properties of persons
- [ ] remove template content (posts and such)
- [ ] limit number of authors per bibentry (10? SIGIR forum paper is quite long)
- [X] add impressum
- [ ] fix bibtex encoding errors e.g., "Fr öbe"
