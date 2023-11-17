# 3. Set Criteria for Recommended Static Site Generator

## Status
Accepted

## Context
TTS needs to build a lot of server-rendered websites, both for its own purposes and for other government agencies.

Jekyll has been the popular go-to framework for this work, for a few reasons:
- Many 18F employees were Rubyists
- For a while, it had strong community and institutional support
  - Github uses it as the engine for Github Pages
- Federalist (now Cloud.gov Pages) supports it and USWDS built multiple themes for it, allowing teams to stand up a new government website very quickly
- Markdown pages were relatively easier to edit by a wider variety of TTS employees than other frameworks

In mid-2021 some core maintainers said Jekyll was [in hiatus](https://www.theregister.com/2021/09/14/future_of_jekyll_project_engine/) and recommended other frameworks to switch to. This hasn't been stated on the official website, and the [Jekyll Github repo](https://github.com/jekyll/jekyll) remains active, so Jekyll's future seems unclear.

In addition, a number of TTS employees are unsatisfied with Jekyll because:
- build times have become slower relative to other frameworks
- It’s difficult to support asset rendering (including building USWDS, a common component of our sites) in a way that supports far-futures cache headers
- Building locally in development is difficult to impossible without admin rights, hindering handoff to folks with less computer privileges

For these reasons, we want teams to avoid standing up new Jekyll sites, but we don't yet have consensus on what the alternative should be.

While we don't know what the single alternative to Jekyll should be, we agree that TTS should recommend one alternative over multiple, since a single alternative will be easier for TTS staff to support.

In order to get consensus on the alternative, we should first agree on a criteria for what we need and want in a static site generator.

## Decision

Any static site generator used by TTS needs to:
- be written in a language that many TTS'ers can support
- have sufficient open-source community support and longevity
- be supported by Cloud.gov Pages
- be supported by USWDS
- allow containerization through Docker
- be able to be used for both prototyping and production
- have build times that don't impede development
- not make a11y hard
- have multilingual support
- enable people without specialized engineering skills to edit static content

It would be nice to have:
- built-in support for common compiles-to-web languages, like SASS, ESNext, and TypeScript
- the ability to reuse/share layouts or templates across sites

Current candidates (in no particular order):
- [11ty](https://www.11ty.dev/)
- [Hugo](https://gohugo.io/)
- [Next](https://nextjs.org/)
- [Gatsby](https://www.gatsbyjs.com/)
- [Bridgetown](https://www.bridgetownrb.com/)
- Build our own
- [Middleman](https://middlemanapp.com/)

## Consequences

### Risks of staying with Jekyll
- Degredation of framework and dependencies as community support wanes
- If Jekyll's period of support officially ends, we will be forced to migrate at that point, or risk running deprecated software

## Risks of moving from Jekyll
- We will still need to maintain our many Jekyll apps, for a time
- We will need to decide whether these apps should be deprecated or moved to a new platform
- Moving to a new platform will take a lot of work and support

## Next Steps
The Guild will make a checklist based on these criteria, share it out with teams using these alternatives, and decide what to do next based on the feedback we get.
