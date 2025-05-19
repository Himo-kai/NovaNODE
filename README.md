<sub>NovaNODE</sub>

***It's a Scrapper*** -
 If you've ever played PACMAN<sup>TM</sup>. It's like that but with no 8-bit soundtrack. It takes    everything.

***Dig in Deep*** -
You set the crawl depth and page limits. Want to scrape 3 levels deep? Fine. Want to hit 500 pages? Done. Your call.

***Formatted for A.I Assistance*** -
Output is formatted for AI consumption. No extra processing needed - dump it straight into your models and they'll understand it. Saving those precious Tokens used on web analysis.

***Documentation*** -
Works especially well on documentation sites like Redis.io. Automatically identifies API docs, parameters, and examples without special configuration.

***Low Profile*** -
Avoid's bot detection, Modifies headers, spoofs fingerprinting, and mimics regular browser behavior. Not foolproof, but effective.

***Simple and Clean*** -
Basic command-line interface. Nothing fancy - just flags that work. Set a few parameters and let it run.

***Nova Sama*** -
Extracts key concepts, terminology, and builds references creating a logical structure for navigation, content, documentation, and code examples all organized separately. So it makes sense when you look at it.

───────────────────────

**HOW TO INSTALL**|

<sup><sup>*Bash*</sup></sup>
```
# Using npm
npm install novanode

# Global installation
npm install -g novanode

# Using yarn
yarn add novanode
```

───────────────────────

**REQUIREMENTS**|

* Node.js 14.x or higher
* Chrome browser installed (or specify custom Chrome path)

───────────────────────

**HOW TO USE**|

<sub>COMMAND LINE</sub>
-
<sup><sup>*Bash*</sup></sup>
```
# Basic usage
novanode https://redis.io/docs

# With options
novanode https://redis.io/docs --depth 3 --pages 50 --output redis-docs

# Help and options
novanode --help
```

<sub>AS A MODULE</sub>
-
<sup><sup>*JavaScript*</sup></sup>
```
const { illuminate } = require('novanode');

// Basic usage
illuminate('https://redis.io/docs')
  .then(outputDir => {
    console.log(`Content extracted to: ${outputDir}`);
  })
  .catch(err => {
    console.error('Extraction failed:', err);
  });

// With options
illuminate('https://redis.io/docs', {
  maxDepth: 3,
  maxPages: 200,
  outputDir: './redis-docs',
  createAiReadyContent: true
});
```

───────────────────────

**EXAMPLES**|

<sub>EXTRACTING DOCUMENTATION SITE</sub>
-
<sup><sup>*JavaScript*</sup></sup>
```
// Extract Redis documentation
illuminate('https://redis.io/docs', {
  maxDepth: 3,
  maxPages: 200,
  followDocLinks: true
});
```

<sub>SINGLE PAGE APPLICATION</sub>
-
<sup><sup>*JavaScript*</sup></sup>
```
// Extract ChatGPT interface
illuminate('https://chat.openai.com/', {
  maxDepth: 1,
  maxPages: 1,
  includeResources: true
});
```


**OUTPUT STRUCTURE**| <sub>NovaNODE</sub>

**output-directory**/<br />
├── pages/               
├── resources/           
├── screenshots/          
├── docs/                
├── Site Name For AI    
│ $~~~~$ $~~~~$ ├── 00_site_overview.json<br />
│ $~~~~$ $~~~~$ ├── 01_documentation.json<br />
│ $~~~~$ $~~~~$ ├── 02_glossary.json<br />
│ $~~~~$ $~~~~$ ├── 03_all_content.json<br />
│ $~~~~$ $~~~~$ └── 04_comprehensive_content.md<br />
├── sitemap.json          
├── resources.json       
└── external-links.csv   

───────────────────────




