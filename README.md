Although I do a fair amount of closed source work, many of my projects are public-access on GitHub and on [JSR](https://jsr.io/user/9d201edf-5d16-4f36-b5a7-28add71c9e5f).

## Qworum

[Qworum](https://qworum.net) is a new variant of the World Wide Web that is especially suitable for applications. This is in contrast to the current Web that is still fundamentally a content platform, even if nowadays Web pages have significant amounts of JavaScript sprinkled on them.

Qworum is a commercial PaaS/iPaaS hybrid offering that is based on the first API technology to support interactive processes, which in turn is based on a [software patent](https://patents.google.com/patent/US8266632).

[qworum-for-web-pages](https://github.com/doga/qworum-for-web-pages)

## Some of my notable projects

```mermaid
---
title: Dependencies between my projects; some external dependencies are also shown, colored in blue.
---
flowchart TD
    subgraph all[" "]
        subgraph javascript["JavaScript (use in browsers and in off-browser runtimes)"]
            punycode
            IRI
            language
            rdf-dataflow["rdf-dataflow"]
            rdf-to-text
            n3["N3.js"]:::external
        end

        subgraph browser["Web browser"]
            rdf-viewer-chrome-extension
            qworum-for-web-pages
        end

        subgraph webapps["Qworum webapps"]
            qworum-application-template
            qworum-application-template-with-semantic-data
        end

        subgraph deno["🦕 Deno"]
            graphdb-sparql-client
            qgeminiserver
            geminispace-jsdoc-server
        end

        rdfjs-types["rdfjs/types"]:::external
    end

    %% ═══ Edges ═══
    IRI -- import --> punycode
    language -- import (unnecessary) --> IRI
    rdf-dataflow -- import --> IRI
    rdf-dataflow -- import --> language
    rdf-to-text -- external import --> n3
    rdf-to-text -- import --> IRI
    rdf-to-text -- import --> language
    rdf-viewer-chrome-extension == pulled-in import ==> language
    rdf-viewer-chrome-extension == pulled-in import ==> IRI
    rdf-viewer-chrome-extension == pulled-in import ==> punycode
    rdf-viewer-chrome-extension == pulled-in import ==> rdf-to-text
    rdf-viewer-chrome-extension == pulled-in external import ==> n3
    geminispace-jsdoc-server -- import --> qgeminiserver
    graphdb-sparql-client -- pulled-in import --> IRI
    graphdb-sparql-client -- pulled-in external import --> rdfjs-types
    qworum-for-web-pages -. import .-> rdf-dataflow
    qworum-for-web-pages -. import .-> IRI
    qworum-for-web-pages -. import .-> n3
    qworum-application-template -- import --> language
    qworum-application-template -- import --> qworum-for-web-pages
    qworum-application-template-with-semantic-data -- import --> language
    qworum-application-template-with-semantic-data -- import --> qworum-for-web-pages

    %% ═══ Click targets ═══
    click punycode "https://github.com/doga/punycode"
    click IRI "https://github.com/doga/IRI"
    click language "https://github.com/doga/language"
    click rdf-dataflow "https://github.com/doga/rdf-dataflow"
    click rdf-to-text "https://github.com/doga/rdf-to-text"
    click rdf-viewer-chrome-extension "https://github.com/doga/rdf-viewer-chrome-extension"
    click n3 "https://github.com/rdfjs/N3.js"
    click rdfjs-types "https://github.com/rdfjs/types"
    click graphdb-sparql-client "https://jsr.io/@arma/graphdb-sparql-client"
    click geminispace-jsdoc-server "https://jsr.io/@arma/geminispace-jsdoc-server"
    click qgeminiserver "https://jsr.io/@arma/qgeminiserver"
    click qworum-for-web-pages "https://github.com/doga/qworum-for-web-pages"
    click qworum-application-template "https://github.com/doga/qworum-application-template"
    click qworum-application-template-with-semantic-data "https://github.com/doga/qworum-application-template-with-semantic-data"

    %% ═══ Classes ═══
    classDef external fill:#1e3a8a,stroke:#1e40af,stroke-width:2px,color:#dbeafe,rx:6,ry:6
    classDef buggy fill:#fee2e2,stroke:#dc2626,stroke-width:2px,color:#991b1b,rx:6,ry:6

    %% ═══ Styles ═══
    %%style javascript fill:#FEF3C7,stroke:#D97706,stroke-width:2px,color:#78350F,rx:6,ry:6
    %%style browser fill:#EDE9FE,stroke:#7C3AED,stroke-width:2px,color:#4C1D95,rx:6,ry:6
    %%style deno fill:#ECFEFF,stroke:#0891B2,stroke-width:2px,color:#164E63,rx:6,ry:6

    style deno fill:#58251C,stroke:#333,stroke-width:2px,color:white,rx:6,ry:6,opacity:0.9;
    style browser fill:#58251C,stroke:#333,stroke-width:2px,color:white,rx:6,ry:6,opacity:0.9;
    style javascript fill:#58251C,stroke:#333,stroke-width:2px,color:white,rx:6,ry:6,opacity:0.9;
    style webapps fill:#58251C,stroke:#333,stroke-width:2px,color:white,rx:6,ry:6,opacity:0.9;
    style all fill:#444,stroke:#333,stroke-width:2px,color:white,rx:6,ry:6,opacity:0.9;

    %%linkStyle 3 stroke:#ff3,stroke-width:4px,color:red;
```

## What I am working with

<p align="left">
<a href="https://qworum.net" target="_blank" rel="noreferrer"><img src="./logos/Qworum-logo.svg" height="36" alt="Qworum" /></a>
<a href="https://developer.chrome.com/docs/extensions/" target="_blank" rel="noreferrer"><img src="./logos/chrome-extensions-logo.svg" height="36" alt="Google Chrome extensions" /></a>
<a href="https://deno.com/" target="_blank" rel="noreferrer"><img src="./logos/deno.svg" width="36" height="36" alt="Deno" /></a>
<a href="https://www.w3.org/2011/rdf-wg/wiki/Main_Page" title="RDF Resource Description Language"><img style="border:0px;" width="36" src="./logos/rdf.svg" alt="Turtle semantic data format"/></a>
<a href="https://graphdb.ontotext.com/" title="GraphDB from Ontotext"><img style="border:0px;" width="36" src="./logos/GraphDB-logo.svg" alt="GraphDB logo"/></a>
<a href="https://www.typescriptlang.org/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/typescript-colored.svg" width="36" height="36" alt="TypeScript" /></a>
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/javascript-colored.svg" width="36" height="36" alt="JavaScript" /></a>
<a href="https://developer.mozilla.org/en-US/docs/Glossary/HTML5" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/html5-colored.svg" width="36" height="36" alt="HTML5" /></a>
<a href="https://www.w3.org/TR/CSS/#css" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/css3-colored.svg" width="36" height="36" alt="CSS3" /></a>
<a href="https://www.oracle.com/java/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/java-colored.svg" width="36" height="36" alt="Java" /></a>
<a href="https://www.ruby-lang.org/en/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/ruby-colored.svg" width="36" height="36" alt="Ruby" /></a>
<a href="https://www.ruby-lang.org/en/" target="_blank" rel="noreferrer"><img src="./logos/ruby-on-rails.svg" width="36" height="36" alt="Ruby on Rails" /></a>
<a href="https://dart.dev/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/dart-colored.svg" width="36" height="36" alt="Dart" /></a>
<a href="https://flutter.dev/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/flutter-colored.svg" width="36" height="36" alt="Flutter" /></a>
<a href="https://firebase.google.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/firebase-colored.svg" width="36" height="36" alt="Firebase" /></a>
<a href="https://www.postgresql.org/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/postgresql-colored.svg" width="36" height="36" alt="PostgreSQL" /></a>
<a href="https://www.mongodb.com/" target="_blank" rel="noreferrer"><img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/skills/mongodb-colored.svg" width="36" height="36" alt="MongoDB" /></a>
<a href="https://stripe.com/en-ch/connect" target="_blank" rel="noreferrer"><img src="./logos/stripe.svg" height="36" alt="Stripe Connect" /></a>
<a href="https://developers.google.com/maps" target="_blank" rel="noreferrer"><img src="./logos/google-maps.svg" height="36" alt="Google Maps Platform" /></a>
<a href="https://www.docker.com/" target="_blank" rel="noreferrer"><img src="./logos/docker.svg" height="36" alt="Docker" /></a>
<a href="https://www.netlify.com" target="_blank" rel="noreferrer"><img src="./logos/netlify.svg" height="33" alt="Netlify" /></a>
<a href="https://cloud.google.com/" target="_blank" rel="noreferrer"><img src="./logos/google-cloud.svg" height="36" alt="Google Cloud" /></a>
</p>
