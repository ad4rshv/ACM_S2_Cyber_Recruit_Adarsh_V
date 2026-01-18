Problem Description
 
 -This challenge was an HTML-based CTF task where the flag was hidden inside the source code instead of being visible on the webpage. The challenge had multiple Base64-encoded fragments placed across different         parts of the HTML file such as comments, CSS, SVG tags, hidden elements, and JavaScript.
  Along with real fragments, the file also contained decoys, placeholders, and noise, making it necessary to carefully analyze the source and decide what was useful.

  Approach

-I first opened the text/HTML file provided in the challenge and understood that the task was about finding hidden Base64 data, not interacting with a webpage.
 Since I was not very familiar with HTML at the beginning, I taught myself basic HTML, mainly focusing on how flags are hidden in CTF challenges (comments, hidden tags, attributes, SVG, CSS, and JavaScript).
-After that, I carefully went through the entire source code instead of immediately decoding everything.
-While reading the source, I focused on the clues provided by the author, such as:
   *The title “Complicated Base64 Hunt”, which suggested that the flag was split into multiple parts.
   *Comments indicating that Base64 was hidden in CSS comments and pseudo-elements, showing that data can be hidden in non-obvious places.
   *Mentions of PART, fragment, dummy, and placeholder, which helped distinguish real data from noise.
-I shortlisted Base64-looking strings and avoided decoding blindly. Instead, I categorized decoded results into:
   *Content (possible real flag fragments)
   *Labels (information about structure or ordering)
-One important learning moment was handling split Base64 strings. Some Base64 was split across multiple <span> elements. I realized they had to be combined first and decoded only once, instead of decoding each       piece separately.
-In the JavaScript section, several variables were clearly marked as noise or placeholders. I learned that ignoring irrelevant data is important.

Analysis

-After filtering out decoys and placeholders, I observed a consistent pattern where valid Base64 fragments decoded into sequential parts of the flag. These fragments appeared across different sections of the source code, confirming they were meant to be combined.

Final Flag

-After decoding and assembling the correct fragments, the final flag obtained was:
                 PArt1PArt2PArt3PArt4
