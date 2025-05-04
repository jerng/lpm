# Literate Programming Management
This repository probes the solution space, of integration between LP and modern QA in SWE. As I'm not a professional SWE, this should be a playpen for personal development.

My understanding of LP ([literate programming](https://en.wikipedia.org/wiki/Literate_programming)), is that it's intended as a solution along the HCI ([human-computer interaction](https://en.wikipedia.org/wiki/Human%E2%80%93computer_interaction)) axis of the QA ([quality assurance](https://en.wikipedia.org/wiki/Quality_assurance)) problem space, in SWE ([software engineering](https://en.wikipedia.org/wiki/Software_engineering)).

###### Maybe Relevant
- [nbdev](https://nbdev.fast.ai/) : a notebook-driven IDE, so-far mainly for Python development
- [entangled](https://entangled.github.io/l) : literate programming in Markdown, running on a Python stack

### Architecture : Initial Draft

- **Feature 1.** "basically literate programming" : markdown with tagged code blocks (A) -> renders [ docs (B) + normalised static code (C) ] 
- **Feature 2.** "in a browser editor" : three panes, A, B, C side by side. 
- **Feature 3.** "render to SCM" : A,B,C all flush to disk in one repo, and (build + test + run + SCM : screen pops up to close the loop) 
- **Feature 4.** A superset of **Feature 1.** is objectifying (A) within an agile project management tool ontology & workflow (can just imagine PivotalTracker for illustrative purposes). Which basically shrinks the complexity of documentation : the same tool used to describe spec, can be used to implement pseudo-code, then code-snippets, then proof of concepts, then finally the final A,B,C all within the same app.

#### Discussion

It was offered, "this already does the job : [https://code.visualstudio.com/docs/datascience/jupyter-notebooks](url)"
> My comments
> - Nice. I guess then the missing concern is Feature 4. Where this actually links notebooks into production code under SCM. Is that also done?
> - I know what notebooks are - I've seen these 12 years ago. But it's not apparent how this could be used seamlessly, as the actual IDE, with CI/CD, for an entire CRUD app. ( which is extending "literate programming" from "programming a little app" to "programming a big app").
> - The original LP is Feature 1. ( Knuth's syntax, not MD ). And the intention is that you do the entire software development process this way. But nowadays we have more sophisticated workflows "CI/CD" etc. The point I have is just how to glue both together. Because it "is" the same problem.

It was offered, "You do not want to know that people has built an entire production setup just based on notebooks"
> My comments
> - Because the wiring to do it properly does not exist. LP is for solving a comprehension/communication problem along the HCI axis, of the quality problem space which already contains ci/cd etc.
> - I think the missing function is : 
>   - existing lit prog : `git checkout [ lit prog, docs, source ] -> edit [ lit prog ] -> compose [ docs, source ] -> build, test [ docs, source ] -> git commit [ lit prog, docs, source ]`
>   - migration to lit prog : `git checkout [ docs, source ] -> decompose [ lit prog, docs, source ] -> edit [ lit prog ] -> ( ditto )`
