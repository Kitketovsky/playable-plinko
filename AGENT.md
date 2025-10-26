# Playblae

## Technical Requirements

- **Format:** Single HTML file with embedded resources
- **Size:** Maximum 5 MB
- **External dependencies:** Prohibited (no links to external files via imports)
- **Cannot use XMLHttpRequest**
- **Cannot include mraid.js**
- **Cannot load external resources (images, fonts, scripts)**
- **Cannot make HTTP requests**
- **Compression:** All assets (images, sounds) must be embedded via data-URI
- **Redirect:** Only through FbPlayableAd.onCTAClick() without parameters
- **Upload format:** HTML file

## Functional Requirements

### Call to Action Handler

Mandatory implementation of install button click:

```javascript
document
  .getElementById("install-button")
  .addEventListener("click", function () {
    if (typeof FbPlayableAd !== "undefined" && FbPlayableAd.onCTAClick) {
      FbPlayableAd.onCTAClick();
    }
  });
```

### Game Configuration

All modifiable parameters must be extracted into a configuration object:

```javascript
const GAME_CONFIG = {
  gameplay: {
    initialBalance: 15,
    betAmount: 5,
    targetBalance: 250,
    maxAttempts: 3,
    // …other
  },
  texts: {
    currency: "$",
    balance: "Balance",
    bet: "Bet",
    win: "Win!",
    congratulations: "Congratulations!",
    youWon: "You Won",
    tryAgain: "Try Again",
    freeSpins: "50 free spins",
    install: "Install",
    claim: "Claim",
    play: "Play",
    cashOut: "Cash out",
    // ...other
  },
};
```

### Game Scenario

The game must have a predetermined outcome (must be set via config)

## Tech Stack

- p5 - Canvas API wrapper for easier drawing
- matter-js - 2D rigid body physics engine for the web

## Workflow Recommendations

- use context7 MCP when using libraries for up-to-date documentation
- use sequential-thinking MCP and to-do lists before creating a new feature
