MEMO: FRAUD_LOG_V3
STATUS: BUSTED / PANIC_MODE_DETECTED SUBJECT: HEXSEC & HACXGPT MANIPULATION TRACKER
INSTRUCTIONS:
- Process Conversation 1 & 2 to establish the baseline: Deceptive marketing and "API-wrapper" architecture.
- Note the shift: Initial admission of guilt and refund offers (evidence of fraud).

#  Process Conversation 3 to analyze the meltdown:
- Deletion of confessions.
- Failed technical defense (Static XSS denial).
- Thread locking and "Spam" labeling as an exit strategy.

AUDIT CONCLUSION: Account name changes and deletions are logged. The connection via shared TLD and unique code patterns remains persistent. The "Wall of Shame" is archived.
LOG END.

#####################################################################################################################################################################################

Orginal Copnversation Backup on 10.02.2026 @ 14:41 from VolkanSah below

#####################################################################################################################################################################################
VolkanSah
opened last week · edited by VolkanSah

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
Activity
Next
VolkanSah
VolkanSah commented last week
VolkanSah
last week
Author

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
BlackTechX011
BlackTechX011 commented last week
BlackTechX011
last week · edited by BlackTechX011
Collaborator

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
BlackTechX011 commented last week
BlackTechX011
last week
Collaborator

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
BlackTechX011
changed the title [-]Critical Disclosure: Technical Deception, API Reselling & Fake "Custom Model" Claims[/-] [+]😂 "Critical Disclosure: Technical Deception, API Reselling & Fake "Custom Model" Claims"[/+] last week
BlackTechX011
BlackTechX011 commented last week
BlackTechX011
last week
Collaborator

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
BlackTechX011
BlackTechX011 commented last week
BlackTechX011
last week · edited by BlackTechX011
Collaborator

This project has 800+ stars because it does exactly what it claims to do - it's a working CLI tool that provides unrestricted AI access through public APIs with jailbreak prompts. People use it, trust it, and contribute to it because they find value in it.

The code is completely open source. Every single line is available for audit. If there was something malicious or deceptive, the community would have called it out long ago.

You came in here with dramatic accusations, zero proof, and claims of "3-minute hacks" you can't demonstrate. That's not a security audit - that's FUD.

This project will continue to develop and grow regardless of baseless accusations from people who clearly didn't even read the code they're criticizing.
BlackTechX011
assigned
BlackTechX011
and unassigned
BlackTechX011
last week
BlackTechX011
added
invalidThis doesn't seem right
last week
VolkanSah
VolkanSah commented last week
VolkanSah
last week · edited by VolkanSah
Author

"Nice try, BlackTechX. First you post a submissive apology admitting your 'misleading language' and offering refunds because you got caught red-handed, and then you will delete it to play the 'tough guy'? I have the logs and screenshots of your initial confession. Editing your response won't save your reputation.

Let’s talk technicals since you’re 'laughing':

    The 'Static Site' Myth: You think a static site can't be XSSed? That shows exactly why you shouldn't run a security project. DOM-based XSS doesn't need a database. Your Xc function and the way you handle URL parameters/local storage to 'persist' session data is a playground for client-side injection. If a user clicks a crafted link, I can exfiltrate their localStorage (where they keep their API keys) to my webhook. That is how you 'XSS a static site', genius.

    Prototype Pollution: Your React build uses outdated utility patterns. I can pollute the Object.prototype via your state management, leading to arbitrary code execution in the context of the user's browser.

    The Confession: Why did you offer refunds in your first comment? Because you know that selling a system-prompt-wrapper as a 'Custom Trained Production Model' is fraud. You admitted the 'Production Model' isn't in this repo – because it doesn't exist. It's just a different system prompt on a paid API.

    The 'AI Spam' Defense: Calling a technical audit 'AI-written' is the last refuge of someone who can't explain their own Xc function.

Fact: You are a reseller of free/cheap APIs. Fact: You are using GitHub as a funnel for a Telegram scam. Fact: Your 'Security' site is built by someone who doesn't understand DOM-XSS.

Keep laughing while the DSA report and the GitHub Abuse team process your 'static' infrastructure. I don't need to 'hack' you – you're already self-destructing by lying to your 800+ stars."

USE LESS AI AND MORE BRAIN!
VolkanSah
VolkanSah commented last week
VolkanSah
last week · edited by VolkanSah
Author

"I gave you a chance to fix it and come clean. You chose to delete your confession and play the 'tough guy' instead. Bad choice. Now, welcome to the Wall of Shames. Your scam and your technical incompetence are now public recorded. The GitHub community doesn't forget.

Stay 'static' while your reputation evaporates. 🌵🔥"
Hackerongithub
Hackerongithub commented last week
Hackerongithub
last week

Pure stupid
VolkanSah
changed the title [-]😂 "Critical Disclosure: Technical Deception, API Reselling & Fake "Custom Model" Claims"[/-] [+]"Critical Disclosure: Technical Deception, API Reselling & Fake "Custom Model" Claims"[/+] last week
Hackerongithub
Hackerongithub commented last week
Hackerongithub
last week

Bro perform the hack I love to see ittttt
VolkanSah
VolkanSah commented last week
VolkanSah
last week · edited by VolkanSah
Author

    Bro perform the hack I love to see ittttt

It not legal bro 😄 and thats not security!
5 remaining items
BlackTechX011
BlackTechX011 commented 5 days ago
BlackTechX011
5 days ago
Collaborator

I'm addressing every claim you've made one last time.

On Deleted Content:
I have not deleted any content. Every comment I've posted remains visible in this thread. Anyone can verify this by checking the edit history. If you claim otherwise, provide screenshots with timestamps.

On Your Claims:
You've made numerous accusations:

    Security vulnerabilities in the website
    Fake "custom model" claims
    API reselling scam
    Fraudulent business practices

Yet you've provided zero evidence for any of these claims.

On Proof:
You claim you can't demonstrate your findings due to "legal boundaries." That's a convenient excuse.

I am the owner of this infrastructure. I have given you explicit written permission to conduct security research and demonstrate any vulnerabilities you claim exist. There are no legal barriers.

You either have proof or you don't. Stop hiding behind excuses.

On the Model:
You demand proof that our model exists. Here's the documentation: https://hacxgpt.com/models/lightning

This page contains technical specifications, benchmarks, and architecture details. Review it, then come back with specific technical critiques if you have any.

On This Project:
Let me be absolutely clear: this project will continue to develop regardless of your accusations.

We have:

    we have many users on who find value in this tool
    Active development and contributions
    Open source code available for anyone to audit
    Real users using the service daily
    Clear documentation

Your "Wall of Shame" means nothing. Your unproven claims mean nothing. Your threats mean nothing.

The Simple Challenge:
Prove anything you've claimed:

    Show the security exploits
    Demonstrate the vulnerabilities
    Prove the model doesn't exist
    Provide evidence of fraud

If you can't provide evidence, then you're just spreading FUD (Fear, Uncertainty, Doubt) with no substance.

Moving Forward:
This project continues. Development continues. Users continue to benefit from it.

You can either provide actual evidence for your claims, or you can continue posting empty accusations that nobody will take seriously.

The choice is yours.
VolkanSah
VolkanSah commented 5 days ago
VolkanSah
5 days ago
Author

Your write realy fast! How?
BlackTechX011
BlackTechX011 commented 5 days ago
BlackTechX011
5 days ago
Collaborator

its not fast
BlackTechX011
changed the title [-]"Critical Disclosure: Technical Deception, API Reselling & Fake "Custom Model" Claims"[/-] [+]Invalid Report: Allegations Without Proof[/+] 5 days ago
BlackTechX011
BlackTechX011 commented 5 days ago
BlackTechX011
5 days ago
Collaborator

This thread is being locked early due to continued unsubstantiated accusations and lack of good-faith engagement. The 48-hour deadline for evidence stands.
BlackTechX011
closed this as completed5 days ago
VolkanSah
VolkanSah commented 5 days ago
VolkanSah
5 days ago
Author

@BlackTechX011 – Let’s talk about your exit strategy.

Since you claim you’re not using an AI to write your scripts, let’s focus on the reality of your situation. You are operating a financial fraud (Bait-and-Switch) using US-based infrtastructure (GitHub, Cloudflare, OpenAI/DeepSeek via API).

As a veteran in this industry, let me tell you how this ends: You aren't hiding in Ulaanbaatar. You are using services that comply with US federal law. The moment the "Deceptive Content" and "Financial Fraud" reports are processed, your "Lightning" architecture becomes a federal case file. The FBI’s IC3 division loves cases likle this because you’ve left a trail of breadcrumbs across every major US provider.

How we expected a professional Code Auditor to behave: When a senior researcher points out a flaw (like your DOM-XSS or your API-wrapping), a professional developer says: "Thank you, let me check the logs and the architecture." How you behaved: You deleted evidence, lied abozt your model's origin (despite your own system prompt admitting it’s a wrapper), and tried to bait me into a legal trap by giving "permission to hack."
Your only way out of this mess:

If you want to avoid the "Wall of Shame" becoming your permanent digital legacy (and potentially worse legal consequences), here is what you do:

    Full Disclosure: Admit that "Hacx-Lightning" is a prompt-engineered wrapper and not a custom-trained model.

    Refunds: Stop the Telegram paywall immediately and refund those you’ve misled with the "Custom Model" claim.

    Shutdown: Take down the deceptive marketing pages and the fraudulent "Benchmark" documentation.

Self-report before the providers report you. It’s the only way to keep your name from being blacklisted in the security community forever.

The choice is yours: Be a developer who made a "mistake" and corrected it, or be the guy whose name is synonymous with a cheap API-scam on the FBI’s radar.

Tick-tock. Tick-tock. Tick-tock. Tick-tock. Tick-tock. — Volkan Sah 🌵🔥
BlackTechX011
BlackTechX011 commented 5 days ago
BlackTechX011
5 days ago
Collaborator

Your escalation to legal threats and federal agencies reveals exactly what this is: baseless intimidation because you have no actual evidence.

On Your "Veteran" Status:
You keep claiming authority as a "veteran researcher," yet you've provided zero credentials, zero proof of exploits, and zero technical evidence. Real security researchers don't hide behind threats—they demonstrate vulnerabilities responsibly.

On Legal Threats:
Threatening FBI reports and federal investigations for a legitimate open-source project shows desperation. You're welcome to file whatever reports you want. This project:

    Operates transparently with open-source code
    Clearly documents what it does
    Provides real value to real users
    Violates no laws

If you had actual evidence of fraud, you'd present it instead of making dramatic threats.

On "Exit Strategy":
I don't need an exit strategy. I need you to provide evidence.

You claim:

    DOM-XSS vulnerabilities → Show the exploit
    Fake custom model → Disprove the benchmarks at hacxgpt.com/models/lightning
    Financial fraud → Prove users aren't getting what's advertised
    API wrapper scam → Show that the production model is identical to public APIs

You've had multiple opportunities. You've provided nothing.

On "Deleted Evidence":
This is a lie. Every comment is visible with full edit history on GitHub. Anyone can verify this. Repeating a false claim doesn't make it true.

On "Permission to Hack" Being a "Trap":
This is absurd. Responsible security researchers test systems with permission all the time. The fact that you're calling standard security research practices a "legal trap" proves you have no exploits to demonstrate.

The Reality:
You made bold claims. You can't back them up. Now you're resorting to:

    Legal threats
    Appeals to authority ("veteran researcher")
    Time pressure tactics ("tick-tock")
    Intimidation with federal agencies

None of this is evidence. None of this proves your claims.

What Happens Next:
This project continues to operate and develop. Users continue to find value in it. Your threats and your "Wall of Shame" change nothing.

If you want to file reports with GitHub, Cloudflare, the FBI, or anyone else, go ahead, do it. They'll ask you for the same thing I'm asking for: evidence.

When you can't provide it, this conversation will speak for itself.

Final Statement:
I've given you every opportunity to prove your claims. You've chosen threats instead of evidence. That tells the community everything they need to know about the validity of your accusations.

This issue is now closed.

The project continues.
BlackTechX011
BlackTechX011 commented 5 days ago
BlackTechX011
5 days ago
Collaborator

Let me make this very simple for you:

On Your "Wall of Shame":
I don't care about your wall of shame. Nobody does. You think adding my project to some random list on your GitHub gives you authority? It doesn't.

On Your Technical Claims:
You claim to find XSS in a static, pre-compiled React site hosted on Cloudflare Pages. That alone shows you don't understand basic web architecture.

Static sites don't work the way you think they do. There's no server-side processing. No database. No dynamic content generation. You're looking for vulnerabilities that can't exist in this architecture.

On Your FBI Threats:
You actually think the FBI cares about your "Wall of Shame"? That federal agents are going to investigate a legitimate open-source project because you wrote some dramatic posts on GitHub?

That's delusional.

On Your "Veteran" Status:
Real security researchers provide proof. They demonstrate exploits. They write detailed vulnerability reports.

You? You write threats, make claims you can't back up, and hide behind "legal boundaries" when asked for evidence.

The Bottom Line:

    You have no exploits to show
    You have no evidence of fraud
    You have no technical proof of anything
    You have nothing but empty threats and a "Wall of Shame" nobody cares about

What I Care About:
I care about my users. I care about building a tool that works. I care about continuing development.

What I don't care about: Your wall of shame. Your threats. Your baseless accusations.

We're Done Here:
Add me to whatever list you want. Write whatever posts you want. File whatever reports you want.

This project continues. My users are happy. The code is open source for anyone who wants to audit it.

You're just noise.
VolkanSah
VolkanSah commented 5 days ago
VolkanSah
5 days ago
Author

@BlackTechX011,

Your decision to lock this thread is the loudest confession you’ve made so far. It’s the digital equivalent of slamming the door because you can’t win the argument outside.

Let’s address the psychology of your panic:

    The Ghost in the Machine: You scream for "evidence," yet you ignore your own instructions to your AI. Mentioning "DeepSeek" in your prompt is the technical "DNA" that proves your "Lightning Architecture" is a lie. You aren't a developer; you are a prompt-engineer hiding behind a paywall.

    The Illusion of Authority: You demand my credentials while you hide behind a 34-follower Instagram account and fake benchmarks. You act like a "Hacker," but you behave like a frightened admin. Real authority doesn't need to lock threads to survive a debate.

    The Legal Reality: You think the FBI or Meta needs an "XSS exploit" to take you down? No. They only need Evidence of Fraud. Selling a third-party API wrapper as a "Custom-Trained Model" to 3.6 million people in your Facebook network is a textbook case of Wire Fraud and Consumer Deception.

You gave me 48 hours, but you couldn't even last 4. Your fear is documented. Your "DAN-style" prompt is archived. Your Facebook-scam network is mapped.

You can keep the thread locked, but you can’t lock the internet. The Wall of Shame is your new permanent resume.

Happy Birthday to me. Rest in peace to your project.

— Volkan Sah 🌵🛡️🔥
BlackTechX011
BlackTechX011 commented 5 days ago
BlackTechX011
5 days ago
Collaborator

locked the thread because you provided zero evidence after days of dramatic accusations.

The Facts:

    Open source version uses public APIs (clearly documented)
    Private production model is separate infrastructure
    You've shown no proof of anything you claimed
    No XSS exploit, no evidence of fraud, nothing

Your Tactics:
Threats. FBI claims. "Wall of Shame." Legal intimidation.

None of that is evidence.

Bottom Line:
Do whatever you want. File whatever reports you want. Add me to whatever lists you want.

You have no proof.

You're just noise.

The project continues.
VolkanSah
changed the title [-]Invalid Report: Allegations Without Proof[/-] [+]Busted fraud![/+] 5 days ago
HacxGPT-Official
locked as spam and limited conversation to collaborators 5 days ago
BlackTechX011
changed the title [-]Busted fraud![/-] [+]Invalid Report: Allegations Without Proof[/+] 5 days ago
HacxGPT-Official
deleted a comment from VolkanSah 5 days ago
