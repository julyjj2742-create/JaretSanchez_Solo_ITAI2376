# Reflection
## What Worked Well
One thing that worked really well in my implementation was the overall workflow of the agent. Once I had the text extraction, chunking, embeddings, and FAISS retrieval set up, everything flowed the way it was supposed to. The LangGraph structure also made the logic easier to follow because each step was clearly separated instead of being buried inside one long function. Seeing the agent retrieve the right chunks and generate a grounded summary felt like the system was actually doing what it was designed to do.

## What Did Not Work and How I Handled It
The biggest thing that did not work at first was trying to use Hugging Face models inside Google Colab. I kept running into 401 authentication errors even when the token was correct. After spending a lot of time troubleshooting, I realized it wasn’t worth fighting the environment. Instead, I switched to a local scikit‑learn classifier using TF‑IDF and Logistic Regression. It wasn’t the original plan, but it ended up working out.
## Biggest Technical Challenge and How I Solved It
The hardest technical challenge was getting all the components to work together smoothly, especially the classifier and the retrieval pipeline. The Hugging Face issue forced me to rethink my approach, and that pushed me to build a local classifier instead. Once I made that switch, the rest of the system became more stable. I also had to learn how LangGraph handles state, which took some trial and error, but breaking the workflow into nodes helped me understand how the agent moves through each step.

## Option Switch (Single vs. Multi‑Agent)
I stayed with Option A: Single Agent, which is the same choice I made in my Midterm plan. I didn’t switch to Multi‑Agent because the single‑agent structure already fit the problem well, and I wanted to focus on making the retrieval and summarization pipeline solid instead of adding more complexity.

## What I Would Build Next If I Had Another Semester
If I had more time, I would expand the system to support multiple documents at once and maybe add a simple UI so it feels more like a real tool instead of just a notebook. There’s a lot of room to grow this into a more complete document assistant.
