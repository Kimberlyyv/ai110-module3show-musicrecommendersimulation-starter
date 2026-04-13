# 🎧 Model Card: Music Recommender Simulation

## 1. Model Name  

Give your model a short, descriptive name.  
Example: **VibeFinder 1.0**  

---

## 2. Intended Use  

Describe what your recommender is designed to do and who it is for. 

Prompts:  

- What kind of recommendations does it generate  
- What assumptions does it make about the user  
- Is this for real users or classroom exploration  

---

## 3. How the Model Works  

Explain your scoring approach in simple language.  

Prompts:  

- What features of each song are used (genre, energy, mood, etc.)  
- What user preferences are considered  
- How does the model turn those into a score  
- What changes did you make from the starter logic  

Avoid code here. Pretend you are explaining the idea to a friend who does not program.

---

## 4. Data  

Describe the dataset the model uses.  

Prompts:  

- How many songs are in the catalog  
- What genres or moods are represented  
- Did you add or remove data  
- Are there parts of musical taste missing in the dataset  

---

## 5. Strengths  

Where does your system seem to work well  

Prompts:  

- User types for which it gives reasonable results  
- Any patterns you think your scoring captures correctly  
- Cases where the recommendations matched your intuition  

---

## 6. Limitations and Bias 

Where the system struggles or behaves unfairly. 

Prompts:  

- Features it does not consider  
- Genres or moods that are underrepresented  
- Cases where the system overfits to one preference  
- Ways the scoring might unintentionally favor some users  

One limitation I found is that the scoring system can become heavily dominated by energy if that feature is given too much weight. During my experiment, songs with similar energy levels ranked highly even when they did not match the user’s preferred genre or mood. This can create a filter bubble where energetic songs keep appearing for many different profiles. Another limitation is that the dataset is small, so the same songs can show up repeatedly across multiple recommendation lists.

## 7. Evaluation  

How you checked whether the recommender behaved as expected. 

Prompts:  

- Which user profiles you tested  
- What you looked for in the recommendations  
- What surprised you  
- Any simple tests or comparisons you ran  

No need for numeric metrics unless you created some.

I tested the recommender with four profiles: High-Energy Pop, Chill Lofi, Deep Intense Rock, and Sad but High-Energy. Before the experiment, the system balanced genre, mood, and energy in a way that made the results feel more targeted to each profile. The Chill Lofi profile produced the most accurate results because the top songs matched the intended genre, mood, and energy level very closely. The Deep Intense Rock and Sad but High-Energy profiles showed that when the dataset has fewer exact matches, the system starts relying more on energy similarity.

For my experiment, I reduced the genre match weight from +2 to +1 and increased the energy similarity weight from a maximum of +2 to a maximum of +4. After this change, the recommendations became more driven by energy than by genre. Songs like Gym Hero, Storm Runner, Neon Pulse, and Sunrise City appeared more often across different profiles because their energy levels were very close to the target values. This made the recommendations more varied in one sense, but it also made different profiles feel less distinct from each other.

## 8. Future Work  

Ideas for how you would improve the model next.  

Prompts:  

- Additional features or preferences  
- Better ways to explain recommendations  
- Improving diversity among the top results  
- Handling more complex user tastes  

---

## 9. Personal Reflection  

A few sentences about your experience.  

Prompts:  

- What you learned about recommender systems  
- Something unexpected or interesting you discovered  
- How this changed the way you think about music recommendation apps  
