<h1>
    <center>
        Abhishek Patel
    </center>
</h1>
<h4>
    <center>
        Github: @abhishekpatel946
    </center>
    <center>
        Email: abhishekpatel@gmail.com
    </center>

</h4>

</br></br>

### Problems

1. How to upgrade node version 16.20.0 to 18+ with its dependencies

```sh
git clone https://github.com/PichiFinance/challenge
```

> Clone the repository and install the dependencies but getting the below error message with existing older dependencies.

```sh
    npm install with --legacy-peer-deps
or
    npm install                       
    npm ERR! code ERESOLVE
    npm ERR! ERESOLVE unable to resolve dependency tree
    npm ERR! 
    npm ERR! While resolving: mvp_v2@0.1.0̌
    npm ERR! Found: graphql@16.7.1
    npm ERR! node_modules/graphql
    npm ERR!   graphql@"^16.0.1" from the root project
    npm ERR! 
    npm ERR! Could not resolve dependency:
    npm ERR! peer graphql@"^15.6.0" from ra-data-graphql@3.19.11
    npm ERR! node_modules/ra-data-graphql
    npm ERR!   ra-data-graphql@"^3.19.1" from the root project
    npm ERR! 
    npm ERR! Fix the upstream dependency conflict, or retry
    npm ERR! this command with --force or --legacy-peer-deps
    npm ERR! to accept an incorrect (and potentially broken) dependency resolution.
    npm ERR! 
    npm ERR! 
    npm ERR! For a full report see:
    npm ERR! /Users/abhishekpatel/.npm/_logs/2024-06-25T14_39_04_178Z-eresolve-report.txt

    npm ERR! A complete log of this run can be found in: /Users/abhishekpatel/.npm/_logs/2024-06-25T14_39_04_178Z-debug-0.log
```

### Solutions

1. Upgrade the node & its dependencies

```sh
    Key changes and notes:

    Added "engines" field to specify Node.js 18.x or higher.
    Updated all dependencies to their latest compatible versions.
    Removed crypto, fs, path, and request as they are built-in Node.js modules or deprecated.
    Removed ndb as it's a development tool and might not be necessary.
    Updated React to version 18.
    Updated react-scripts to version 5.
    Updated dev dependencies, including moving to the latest major versions of autoprefixer, postcss, and tailwindcss.
    Removed --openssl-legacy-provider from build and test scripts as it's not needed for Node.js 18+.

    After updating the package.json, you should:

    Delete the package-lock.json file and node_modules directory.
    Run npm install to install the updated dependencies.
    Test your application thoroughly, as some of these updates might introduce breaking changes, especially the major version updates like React 18.

    Would you like me to explain any of these changes or provide guidance on potential migration steps for specific libraries?
```

Here is the list of changes I've made linked with this commit: <https://github.com/abhishekpatel946/pitchi-finance-challange/commit/66060681263b96fffbd711f9fa2520b7f68672ec>

</br></br>

### Problems

2. Analysis of current features and what could be next feature for our project.

### Solutions

2. I explore the entire codebase and found some optimizations and refactoring opportunities. I also run the project and explore the game on browser, read the "whitepaper" & "terms and conditions" section to learn more about the concepts.

> And finally I have the idea that I shared below with you:

### My Idea for the "Sheep Game"

My idea is to introduce a dog character adds an interesting layer of complexity and strategy to the Wolf Game. Let's map this concept to the existing game mechanics and explore how it would affect the tokenomics and risk-reward factors:

1. Dog NFT Introduction:
   - Similar to Sheep and Wolves, Dogs could be minted using $WOOL or ETH.
   - Dogs would have unique traits, possibly including a "Guard Strength" attribute (similar to Wolves' Alpha).

2. Dog Mechanics:
   - Staking: Dogs can be staked to protect Sheep in the Barn.
   - Protection Tax: 10% of protected Sheep's $WOOL earnings go to the developer community.
   - Combat System: When Wolves attempt to attack or kidnap Sheep, Dogs have a chance to prevent it based on their Guard Strength.

3. Risk-Reward Factors:
   - For Sheep owners:
     - Risk: 10% tax for protection, potential loss of staking if Dog dies.
     - Reward: Increased security for $WOOL earnings and reduced risk of kidnapping.
   - For Dog owners:
     - Risk: Potential loss of Dog NFT if it dies in combat.
     - Reward: Portion of protection tax (could be distributed among staked Dogs).
   - For Wolf owners:
     - Risk: Reduced success rate for attacks and kidnappings.
     - Reward: Higher payoff when successfully overcoming Dog protection.

4. Tokenomics Adjustments:
   - Modify $WOOL distribution:
     - 70% to Sheep owners (down from 80%)
     - 20% to Wolf tax (unchanged)
     - 10% to Developer community (new Dog protection tax)
   - Introduce a new token for Dog rewards, or use $WOOL with a separate distribution mechanism.

5. Game Balance:
   - Dog Guard Strength vs Wolf Alpha: Create a balanced combat system where neither side is overpowered.
   - Dog Lifespan: Implement a mechanism where Dogs have a chance of "dying" during attacks, adding risk for Dog owners.

6. New Actions and Strategies:
   - "Guard Sheep" (Stake Dog): Choose which Sheep to protect.
   - "Train Dog": Possibility to improve Dog's Guard Strength over time.
   - "Heal Dog": Mechanism to restore Dog's health after attacks.

7. Economic Considerations:
   - Dog Minting: Introduce Dogs gradually to maintain game balance.
   - Secondary Market: Dogs would likely have significant value due to their protective capabilities.

8. Smart Contract Modifications:
   - Update staking contract to include Dog staking and protection mechanics.
   - Modify attack/kidnap functions to account for Dog protection.
   - Implement combat resolution system for Wolf vs Dog encounters.

This addition would create a more complex ecosystem:

- Sheep owners must weigh the cost of protection against the risk of loss.
- Dog owners have a new way to earn but with the risk of losing their asset.
- Wolf owners face new challenges but with potentially higher rewards.

The introduction of Dogs adds a defensive strategy to counterbalance the Wolves' offensive role, creating a more dynamic and engaging game environment. It also provides more opportunities for player interaction and strategy, potentially increasing the game's longevity and player engagement.

</br></br>

### Enhancements & Additional (OPTIONAL)

The idea of introducing insurance for dogs in this game ecosystem is quite relevant and can add another interesting layer of strategy and risk management. Let's explore how this could be integrated:

Insurance Mechanism for Dogs:

1. Insurance Purchase:
   - Dog owners can opt to buy insurance for their dogs using $WOOL or a new token.
   - The insurance cost could be a percentage of the dog's initial minting price or a flat rate.

2. Insurance Coverage:
   - If a dog dies while protecting sheep, the owner can claim insurance.
   - The insurance payout would allow the owner to mint a new dog at a discounted rate (e.g., 70-80% of the original cost).

3. Risk-Reward Factor:
   - Risk: Additional cost for insurance premiums.
   - Reward: Reduced financial loss if the dog dies, maintaining protection for sheep.

4. Tokenomics Integration:
   - Insurance Premiums: Could be paid in $WOOL, adding another use case for the token.
   - Insurance Pool: A portion of premiums goes into a pool to cover payouts.

5. Game Mechanics:
   - "Buy Insurance": New action for dog owners.
   - "Claim Insurance": Action to get a new dog after the insured dog dies.

6. Economic Considerations:
   - Insurance prices could fluctuate based on the overall risk in the game (e.g., wolf population, attack frequency).
   - This creates a new economic loop within the game ecosystem.

7. Strategic Depth:
   - Players must weigh the cost of insurance against the risk of losing their dog.
   - It provides a safety net for players, encouraging more participation in the protective aspect of the game.

8. Smart Contract Implications:
   - Implement insurance purchase, premium collection, and claim functions.
   - Track insured status of dogs and manage the insurance pool.

This insurance mechanism aligns well with the existing risk-reward structure of the game:

1. It adds another layer of decision-making for players.
2. It creates a new economic flow within the game.
3. It provides a safety net that might encourage more players to engage with the dog protection mechanic.
4. It adds realism to the game economy, mirroring real-world risk management strategies.

The insurance idea is particularly relevant because:

1. It fits the theme of risk management already present in the game.
2. It provides a middle ground between full loss and full protection.
3. It can help balance the game by making the dog protection strategy more attractive without making it overpowered.
4. It adds another use case for $WOOL or could introduce a new token, enhancing the game's economy.

In conclusion, the insurance concept is a valuable addition that complements the existing mechanics while adding new strategic considerations for players. It enhances the depth of the game without disrupting its core dynamics.
