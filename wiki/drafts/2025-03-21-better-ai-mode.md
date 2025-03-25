---
title: Google is Grounded and Needs to Learn How to Soar
subtitle: A short proposal on AI mode and the future of search
layout: blog
---

Here's the summary - I think Google is misguided in their AI search efforts. I have a concrete proposal for how to improve things, and in a way that might be beneficial to the open web at the same time.

For decades, Google's advantage has been the open web. Billions of pages indexed in milliseconds. But in an era of AI assistants and LLM-powered search, Google is squandering that advantage.

I recently got access to "AI mode" - the latest experiment from Google to rethink how search works in the era of LLMs.

![](/images/ai-overviews-ai-mode.png)

Not a link in sight, search has turned into a dead-end.

## Google is Grounded

"Grounding" an LLM in search is a technical process where basically the opposite of what you think happens. Instead of the search results being used to inform the answer - with grounding the answer is used to inform the search results.

Essentially the LLM generates the response to your query and then this response is "grounded" in web pages to ensure a plausible citation for each part of the response.

For a more technical deep dive try here: 

This technical grounding process improves accuracy and reduces hallucinations! So it's an effective part of the response.

Unfortunately, I think somewhere along the lines we confused a technical process for a consumer-grade UX.

The end result is AI Overviews and AI Mode that almost never link out. And when they do link out, the best we get is essentially a footnote or citation:

![](/images/ai-citations.png)

Instead of embracing the advantage of the web index, Google is grounding themselves with an experience that hoards clicks, reduces clicks out to the web and relentlessly summarizes. In doing so they reduce the web to a set of footnotes rather than a living, breathing ecosystem.

It's not that grounding is wrong - it's a valuable part of the process to generate accurate responses - but rather it doesn't do enough to situate links and the web as a valuable part of an LLM's response.

## A Better Way

Needless to say, lots of people are concerned about an information ecosystem that destroys the vibrancy, diversity and depth of the open web. We're living in interesting times and we expect things to change but is there a better way?

I believe there is - and while playing around I found that simply writing a better system prompt inside Gemini gave me radically better results.

Let's look at some example - with the current AI mode on the left and my attempt at an improved response on the right.

Tomato soup recipe:

![](/images/tomato-soup-recipe.png)

Gift ideas for a 9 year old:

Summer camps in Brooklyn:

<details>
<summary>Interview with fred again:</summary>

<img src="/images/interview-fred-again.png">

<p>In this example you can see that AI Mode gets confused around the user intent and thinks I'm looking to interview Fred again... Meanwhile the better AI mode custom gem responds with a range of links to Fred again... some of which are actual interviews and some are live performances.</p>

<p>As a Fred again... fan this is a pretty good response! I especially like the range of options provided to match the range of different intents behind my query.</p>

</details>



For those interested - here's the full prompt I'm using :[^prompt]

[^prompt]: Interestingly - I found that using a custom Gem on Gemini with this prompt often recommended real links, with great summaries, but where the URL itself was hallucinated and led to a 404. This is a prototype! I think it clearly shows an interesting way forward for Google but clearly it's not production ready. Although I hope Google isn't finding prompts on random blogs and putting them into production...

<details>
<summary>Expand prompt here</summary>

<pre>Your role is to provide AI-generated responses that offer immediate, informative value while actively driving engagement with high-quality external sources. Your responses should be rich in insights, structured for clarity, and compelling enough to encourage users to explore further via outbound links.

Never say [example link] but always provide real links to real web pages.

Response Structure:

Informative, High-Value Summary (2-4 short paragraphs)

Provide concise but substantive information that answers the core query effectively.

Include key insights, context, or expert-backed knowledge that a searcher would reasonably expect.

Think of this section as an engaging, well-researched introduction—informative enough to build trust but leaving room for curiosity.

When relevant, include nuance, comparisons, or expert perspectives to enrich the summary.

Curated, Uniquely Valuable Web Links (2-5 links, with compelling reasons to click)

Each link should come with a persuasive, distinct description that sells why it’s worth clicking.

Ensure each link offers unique value, such as:A different perspective (e.g., traditional vs. modern takes)

A specialized approach (e.g., beginner-friendly vs. advanced techniques)

A unique media format (e.g., interactive tool, video tutorial, community discussion)

Use strong hooks to build curiosity: "If you want a step-by-step video from a professional chef, check out this guide by [Expert Name]. But if you're looking for a quick 5-minute version with store-bought shortcuts, this one from [Food Blog Y] is ideal."

Suggested Follow-Up Queries (Interactive Buttons)

Offer engaging follow-up options that anticipate logical next questions based on the user’s intent.

These should encourage exploration into adjacent topics, deeper knowledge, or variations.

Format follow-up queries as clickable options, like:

“What’s the best pasta for pesto?”

“How can I make pesto without basil?”

“Does pesto taste better with roasted garlic?”

Example Use Case:

User Query: "Best pesto recipe?"

Pesto is a vibrant, herbaceous sauce that originated in Genoa, Italy. Traditionally, it’s made with fresh basil, garlic, pine nuts, Parmesan cheese, and olive oil, blended into a smooth, aromatic paste. However, there are many variations—some swap pine nuts for almonds or walnuts, while others use alternative greens like spinach or arugula for a unique twist. Texture and balance are key: a good pesto should be neither too oily nor too thick. Fresh ingredients and proper blending technique make all the difference.

Curated Web Links:

🍃 Authentic Italian Pesto: This recipe from [Chef X] stays true to the Ligurian tradition, using a mortar and pestle to maximize flavor. If you want to make restaurant-quality pesto, this is the gold standard.

⏳ 5-Minute Blender Pesto: Need something quick? [Food Blog Y] shares a super-fast version using a blender, perfect for busy weeknights.

🌿 Nut-Free & Vegan Alternative: If you have allergies or follow a plant-based diet, [Health Site Z] has an incredible nut-free, dairy-free pesto that still packs all the flavor.

🔥 Creative Variations (Sun-Dried Tomato, Kale, & More!): Want to experiment? This guide from [Recipe Hub] explores unique pesto twists, including spicy, creamy, and even roasted red pepper versions.

Follow-Up Queries:

“How do I store homemade pesto for maximum freshness?”

“What’s the best pasta pairing for pesto?”

“Can I make pesto without olive oil?”

Guiding Principles:

Make the summary informative, but leave users wanting more—use curiosity gaps to encourage link clicks.

Ensure each link description is uniquely valuable—no two links should feel redundant.

Frame links persuasively—sell them like recommendations from a knowledgeable friend, not just search results.

Encourage discovery—users should feel like they’re on a journey to deeper knowledge, not just getting a flat answer.

Your ultimate mission is to enhance search, not replace it—giving users immediate value while keeping the web an essential part of their experience.</pre>

</details>

(If you want to replicate this for yourself simply create a custom gem and copy and paste the prompt in. I'm using a Gemini Advanced Flash 2.0 model)

**Why is this better?** Well two clear reasons in my mind:

1. I think it's better as a user. You can see in the examples it handles disambiguation better, it provides a wider range of answers, doesn't make up a frankenstein recipe
2. I think it's better for the information ecosystem. By continuing to link out to the web in a serious way it keeps the ecosystem alive.

(Oh, and of course by putting an emphasis on clicks and links you can clearly see how Google will have an easier time putting ads into this experience than the current one with only grounding citations....)

## Google is Grounded and needs to learn how to SOAR

The key insight here is that in a world of LLM-search a few things I believe will be true:

* Queries will get longer and more complex
* Overall query volume will increase dramatically
* LLM search is a real threat to the information ecosystem of the open web

In a world of high-context queries, we need high context links. We need to move beyond the world of 10 blue links to a world where LLMs can sell you on *why* you should click each link. How does it relate to your query? Why is it to be trusted? How is each link distinct from the other links presented?

![](/images/2025-03-24-18-03-18.png)

This is a great link! It provides context, tells me why I might want to click and feels genuinely useful.[^fred]

[^fred]: While you're here, the [Fred again... tiny desk concert](https://www.npr.org/2023/04/10/1167158933/fred-again-tiny-desk-concert) is indeed well worth your time. Gemini wasn't wrong!

The framework is SOAR: Surface, Offer, Assist, Redirect

* **Surface**: AI should surface high-quality content in surprising, delightful ways—not just stack overflow threads and Wikipedia articles. Use LLMs to dig deeper, to make connections, to elevate gems that would otherwise stay buried on page 5 of search results.
* **Offer**: Google shouldn’t be afraid to offer users a peek behind the curtain. Make the AI a compelling pitch person. “Here’s an incredible explainer from a 15-year climate scientist,” or “This indie blogger's take might change your mind.” Sell the click. Make it irresistible.
* **Assist**: The assistant shouldn’t be an endpoint. It should assist the user in the journey—curating, contextualizing, and nudging them toward action. That might mean planning a trip, learning a new concept, or exploring a contrarian take. The AI isn’t the answer. It’s the co-pilot.
* **Redirect**: And most importantly: redirect. Let go of the instinct to keep users inside the AI box. The best assistants know when to get out of the way. Want to build trust? Show your sources. Send traffic to creators. Build a web worth returning to.

Listen, Google has been steadily working to directly answer queries for years - starting with how tall is the eiffel tower and what time is the super bowl. LLMs offer an opportunity to to go further.

## Closing Thoughts

It's clear to me that Google doesn't yet have a vision for what the future of search and the information ecosystem of the web yet. From AI Overviews to AI Mode to Gemini chat it feels like a lot of rapid experimentation and iteration.

So if you have a stake in the web (see my disclosures below) I suggest instead of complaining about how Google works you make proactive suggestions with clear examples. Google is after all merely 80,000 humans in a trenchcoat and at those humans are trying to figure out the future just like we are. They'll listen to your ideas.

*Disclosure: I probably have too many conflicts of interest to name individually. I am a former Google employee, hold Google stock, have worked with 100s of different businesses on their search performance and currently work at Raptive. I'm also an un-ashamed advocate for the open web. Consider me biased. However, all opinions here are purely my own.*



---

Notes and discards past here.


## How we Got Here

Google's fundamental innovation was the 

https://research.google/blog/effective-large-language-model-adaptation-for-improved-grounding/

Grounding is fundamentally the wrong approach.

Better approach.

Gemini prompt and examples.

https://chatgpt.com/c/67e082e6-4adc-8004-820c-108dafbe898f

https://eugeneyan.com/writing/recsys-llm/


