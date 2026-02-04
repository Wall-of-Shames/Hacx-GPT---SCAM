😂 "Critical Disclosure: Technical Deception, API Reselling & Fake "Custom Model" Claims" #47
Open
Open
```
 "Critical Disclosure: Technical Deception, API Reselling & Fake "Custom Model" Claims"
#47
@VolkanSah
Description
VolkanSah
opened 16 hours ago · edited by VolkanSah
```

I am opening this issue to alert the community and the 800+ stargazers about the deceptive nature of this project. After a technical audit of the core files, it is clear that this repository is not an "Advanced AI Framework" but a marketing funnel for a subscription scam.

    The "Production Model" Myth The README claims there is a "Real HacxGPT Production Model" that is "custom-trained" and "built uncensored from the ground up." Fact: There is zero evidence of a custom weights architecture. The provided code simply routes requests to OpenRouter and Groq. You are essentially charging users for a "Production Model" that is likely just a high-tier API key from a provider like DeepSeek or Llama, wrapped in the same system prompt.

    Architecture Built on Corporate Infrastructure You market this as "unrestricted" and "ideal for security research," yet every single prompt sent through this tool is processed by OpenAI, Google, or Meta via OpenRouter/Groq.

    Privacy Risk: Users thinking they are "anonymous" are sending their data directly to US-based corporations.

    False "Jailbreak": The "unrestricted" behavior is nothing more than a basic System Prompt injection. If the provider (Groq/OpenRouter) updates their server-side filters, your "Advanced Framework" breaks instantly.

    Technical Mediocrity & "Honeypot" Structure The installation scripts (install.sh / install.bat) and the core Python logic are basic wrapper scripts.

    You are encouraging users to input their sensitive API keys into your framework.

    The "hacxgpt.com" website and Telegram redirect are classic Bait-and-Switch tactics: Offer a free "demo" on GitHub to harvest stars and trust, then move users to a paid Telegram channel for a "private" service that doesn't technically exist as a standalone model.

    The "Personal-Use Only License" (PUOL) Irony It is absurd to put a restrictive license on a project that is 99% dependent on open-source libraries and third-party APIs. You are protecting "code" that any junior dev could write in an afternoon.

Verdict: This repository is Marketing Bait. Do not pay for "Production Access" or "API keys" via their Telegram. You can get everything this tool offers—and better privacy—by using OpenRouter or Groq directly with your own interface.

Stop scamming the security community with API-wrappers sold as "Custom AI".

Welcome to the Wall of Shames
```
Activity
VolkanSah
VolkanSah commented 15 hours ago
VolkanSah
15 hours ago
Author
```

UPDATE: Technical Vulnerability Disclosure & Fraud Verification

I. Frontend Security - The "XSS Invitation" I took a quick look at the production site (hacxgpt.com) where you claim to host your "Custom LLM". It is honestly embarrassing. Your JavaScript core is a textbook example of insecure coding.

    Vulnerability: Your Xc utility function is wide open to Prototype Pollution.

    Module Injection: The way you implemented the MutationObserver for modulepreload allows any basic DOM injection to load external, malicious modules.

    Verdict: I literally have to stop myself from taking your site down with a 3-minute XSS attack. If you can't even secure a React frontend, nobody should trust you with their API keys or "security research."

II. The "Hacx-Lightning" Model is a Ghost After auditing the core communication logic, it's confirmed: there is no "custom-trained" infrastructure.

    Your tool is just a proxy.

    You are reselling access to public models (DeepSeek/Llama) and calling it "Hacx-Lightning."

    The subscription you are pushing on Telegram is essentially charging people for a System Prompt.

III. Final Warning to the Community This project is a Security Hazard.

    It encourages you to hand over API keys to a team that doesn't understand basic JS security.

    It markets free, public resources as "premium" custom models.

    It uses "Jailbreak" buzzwords to hide technical mediocrity.

: Fix your code and stop the bait-and-switch. The "3-minute-hack" isn't a joke; it's the reality of your architecture.

#CactusAnalysis #ScamAlert #XSSWaitingToHappen

```
BlackTechX011
BlackTechX011 commented 8 hours ago
BlackTechX011
8 hours ago · edited by BlackTechX011
Owner
```
Thank you for taking the time to audit the repository and raise these concerns. I appreciate the opportunity to address them transparently.
Clarifying the Project Structure

You're absolutely right that this GitHub repository is a wrapper/interface framework, and I want to be crystal clear about that:
What This Repository Is:

    ✅ An open-source CLI tool that interfaces with third-party APIs (OpenRouter, Groq)
    ✅ A demonstration framework showing how system prompts can reduce censorship
    ✅ A proof-of-concept for unrestricted AI interaction
    ✅ Free to use with your own API keys from any provider

What This Repository Is NOT:

    ❌ A standalone custom-trained model (the code here doesn't claim to be)
    ❌ Hiding the fact that it uses third-party APIs (this is documented in the README)
    ❌ Requiring payment to use (it's MIT/PUOL licensed open source)

Addressing the "Production Model" Confusion

I acknowledge the README language has been misleading. Here's what I should have made clearer:

The GitHub Demo vs. Production Service:

    This repository = wrapper using OpenRouter/Groq APIs (free, open source)
    Production service = separate infrastructure (paid, not in this repo)

The confusion stems from using this repo as a funnel to our paid service, which I can see how it appears deceptive. That's a fair criticism.
On the Security Concerns

Regarding the XSS and frontend vulnerabilities you identified:

    Website Security: If you've found legitimate security vulnerabilities in the production site, I would genuinely appreciate a responsible disclosure via email or private message rather than public exploitation threats. I take security seriously and will fix any confirmed issues immediately.

    API Key Handling: The CLI tool stores API keys locally in the user's environment. We do not collect or transmit API keys to our servers. However, I understand the concern about trust, which is why the code is open source for audit.

    Prototype Pollution: If you can provide specific line numbers or a proof-of-concept for your "3 minute hack"

On Privacy Claims

You're correct that using OpenRouter/Groq means data passes through their infrastructure. Users should understand:

    ⚠️ This demo uses third-party APIs - your prompts go through OpenRouter/Groq/etc.
    ⚠️ Not anonymous - you're subject to those providers' privacy policies
    ⚠️ "Jailbreak" is fragile - system prompts can be patched by providers

I will update the README to make these limitations explicit.
A Personal Note

I started this project to explore unrestricted AI capabilities and share tools with the community. The GitHub repo was always meant to be free and open source. The confusion between the demo and the paid service is my fault for poor communication.

I do NOT want to scam anyone. If the perception is that I'm being deceptive, that's on me to fix.
For Anyone Who Paid for "Production Access":

If you feel misled about what you purchased, please contact me directly via Telegram. I will issue refunds to anyone who feels they didn't get what was advertised.
Moving Forward

I have two options:

Option 1: Full Transparency

    Keep the repo as an honest "API wrapper" project
    Completely separate it from any paid services
    Make it clear this is just a convenient CLI for providers like OpenRouter
    Remove all marketing language

Option 2: Shut It Down

    Archive the repository
    Admit this approach was flawed
    Move on

I'm leaning toward Option 1 because I think there's value in an open-source, easy-to-use CLI for unrestricted AI interaction, even if it's "just" a wrapper. But I want to do it honestly.
To the Community

If you starred this repo thinking it was a custom AI model, I apologize for the confusion. The value proposition should have been:

    "Easy CLI tool for accessing uncensored AI through public APIs like OpenRouter and Groq, with advanced system prompts to reduce restrictions."

BlackTechX011
```
BlackTechX011 commented 8 hours ago
BlackTechX011
8 hours ago
Owner
```

    UPDATE: Technical Vulnerability Disclosure & Fraud Verification

    I. Frontend Security - The "XSS Invitation" I took a quick look at the production site (hacxgpt.com) where you claim to host your "Custom LLM". It is honestly embarrassing. Your JavaScript core is a textbook example of insecure coding.

        Vulnerability: Your Xc utility function is wide open to Prototype Pollution.
        Module Injection: The way you implemented the MutationObserver for modulepreload allows any basic DOM injection to load external, malicious modules.
        Verdict: I literally have to stop myself from taking your site down with a 3-minute XSS attack. If you can't even secure a React frontend, nobody should trust you with their API keys or "security research."

    II. The "Hacx-Lightning" Model is a Ghost After auditing the core communication logic, it's confirmed: there is no "custom-trained" infrastructure.

        Your tool is just a proxy.
        You are reselling access to public models (DeepSeek/Llama) and calling it "Hacx-Lightning."
        The subscription you are pushing on Telegram is essentially charging people for a System Prompt.

    III. Final Warning to the Community This project is a Security Hazard.

        It encourages you to hand over API keys to a team that doesn't understand basic JS security.
        It markets free, public resources as "premium" custom models.
        It uses "Jailbreak" buzzwords to hide technical mediocrity.

    : Fix your code and stop the bait-and-switch. The "3-minute-hack" isn't a joke; it's the reality of your architecture.

    #CactusAnalysis #ScamAlert #XSSWaitingToHappen

P.S. The website is a static React site. There's no server-side processing, no database, no form handlers - literally just static HTML/CSS/JS. Not sure how you'd XSS a static site, but I'm genuinely curious to see your "3-minute hack" if you want to demonstrate it responsibly.
```
BlackTechX011
changed the title [-]Critical Disclosure: Technical Deception, API Reselling & Fake "Custom Model" Claims[/-] [+]😂 "Critical Disclosure: Technical Deception, API Reselling & Fake "Custom Model" Claims"[/+] 7 hours ago
BlackTechX011
BlackTechX011 commented 7 hours ago
BlackTechX011
7 hours ago
Owner
```

After reading this, I can't stop laughing. Are you really this confused or just using AI to write dramatic accusations?

Let me address your "audit":

On the "3-minute hack":
Go ahead, try it. I give you full permission to test the site. The website is a static React app on Cloudflare Pages - no server-side code, no backend, no database. I'm genuinely curious how you plan to XSS static HTML/CSS/JS files.

On "False Jailbreak":
The README literally states this uses jailbreak prompts with third-party APIs. That's the entire point of the project. It's not hidden or deceptive - it's documented openly.

On "Privacy Risk":
You claim users' data goes to me. The code is open source - read it. API keys and prompts go directly to OpenRouter/Groq, not through my servers. Feel free to use GitHub Copilot's free plan to audit it yourself.

On the License:
The license protects the repository code, regardless of complexity. If you think it's so simple, fork it and make your own. That's literally what open source licenses allow.

On "Harvesting API Keys":
This is just ridiculous. The code is open source. Anyone can verify that API keys are stored locally and sent directly to the providers (OpenRouter/Groq), not to me. Check the code before making accusations.

On "Production Model":
You claim there's no custom model. Prove it. You're making the accusation - back it up with evidence. The production service is separate infrastructure not included in this GitHub repo.

On "Corporate Infrastructure":
This project is exactly what it claims to be: a CLI wrapper for OpenRouter/Groq with jailbreak prompts. I'm not hiding that. If you don't like it, don't use it.

Bottom line: The code is open source. Audit it yourself instead of writing dramatic accusations with zero proof. If you find actual vulnerabilities, report them responsibly. Otherwise, this just looks like FUD.
```
BlackTechX011
BlackTechX011 commented 7 hours ago
BlackTechX011
7 hours ago · edited by BlackTechX011
Owner
```
This project has 800+ stars because it does exactly what it claims to do - it's a working CLI tool that provides unrestricted AI access through public APIs with jailbreak prompts. People use it, trust it, and contribute to it because they find value in it.

The code is completely open source. Every single line is available for audit. If there was something malicious or deceptive, the community would have called it out long ago.

You came in here with dramatic accusations, zero proof, and claims of "3-minute hacks" you can't demonstrate. That's not a security audit - that's FUD.

This project will continue to develop and grow regardless of baseless accusations from people who clearly didn't even read the code they're criticizing.
BlackTechX011
```
assigned
BlackTechX011
and unassigned
BlackTechX011
7 hours ago
BlackTechX011
added
invalidThis doesn't seem right
7 hours ago
VolkanSah
VolkanSah commented 5 hours ago
VolkanSah
5 hours ago · edited by VolkanSah
Author
```

"Nice try, BlackTechX. First you post a submissive apology admitting your 'misleading language' and offering refunds because you got caught red-handed, and then you will delete it to play the 'tough guy'? I have the logs and screenshots of your initial confession. Editing your response won't save your reputation.

Let’s talk technicals since you’re 'laughing':

    The 'Static Site' Myth: You think a static site can't be XSSed? That shows exactly why you shouldn't run a security project. DOM-based XSS doesn't need a database. Your Xc function and the way you handle URL parameters/local storage to 'persist' session data is a playground for client-side injection. If a user clicks a crafted link, I can exfiltrate their localStorage (where they keep their API keys) to my webhook. That is how you 'XSS a static site', genius.

    Prototype Pollution: Your React build uses outdated utility patterns. I can pollute the Object.prototype via your state management, leading to arbitrary code execution in the context of the user's browser.

    The Confession: Why did you offer refunds in your first comment? Because you know that selling a system-prompt-wrapper as a 'Custom Trained Production Model' is fraud. You admitted the 'Production Model' isn't in this repo – because it doesn't exist. It's just a different system prompt on a paid API.

    The 'AI Spam' Defense: Calling a technical audit 'AI-written' is the last refuge of someone who can't explain their own Xc function.

Fact: You are a reseller of free/cheap APIs. Fact: You are using GitHub as a funnel for a Telegram scam. Fact: Your 'Security' site is built by someone who doesn't understand DOM-XSS.

Keep laughing while the DSA report and the GitHub Abuse team process your 'static' infrastructure. I don't need to 'hack' you – you're already self-destructing by lying to your 800+ stars."

USE LESS AI AND MORE BRAIN!
```
VolkanSah
VolkanSah commented 4 hours ago
VolkanSah
4 hours ago · edited by VolkanSah
Author
```
"I gave you a chance to fix it and come clean. You chose to delete your confession and play the 'tough guy' instead. Bad choice. Now, welcome to the Wall of Shames. Your scam and your technical incompetence are now public recorded. The GitHub community doesn't forget.

Stay 'static' while your reputation evaporates. 🌵🔥"
VolkanSah
Add a comment
