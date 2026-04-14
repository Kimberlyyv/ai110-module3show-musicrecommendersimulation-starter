# 🎧 Model Card: Music Recommender Simulation

## 1. Model Name  

Give your model a short, descriptive name.  
Example: **VibeFinder 1.0**  

InTune

## 2. Intended Use  

Describe what your recommender is designed to do and who it is for. 

Prompts:  

- What kind of recommendations does it generate  
- What assumptions does it make about the user  
- Is this for real users or classroom exploration  

This recommender system suggests songs based on a user's music preferences. It generates recommendations by comparing a user’s favorite genre, mood, and energy level with the attributes of songs in the dataset.

The model assumes that users have clear preferences for genre, mood, and energy. It uses these preferences to rank songs that are most similar to what the user wants.

This project is designed for classroom exploration to demonstrate how a basic recommendation system works. It is not intended for real-world music recommendation services.

## 3. How the Model Works  

Explain your scoring approach in simple language.  

Prompts:  

- What features of each song are used (genre, energy, mood, etc.)  
- What user preferences are considered  
- How does the model turn those into a score  
- What changes did you make from the starter logic  

Avoid code here. Pretend you are explaining the idea to a friend who does not program.

The recommender assigns a score to each song based on how well it matches the user’s preferences.

The model looks at three main features of each song: genre, mood, and energy. The user also provides their preferred genre, preferred mood, and a target energy level.

If a song matches the user’s favorite genre, it receives two points. If the mood matches, it receives one point. The system also compares the song’s energy level to the user’s target energy and gives additional points based on how similar they are.

All songs are scored using these rules and then sorted from highest score to lowest score. The top five songs are returned as the recommendations.

## 4. Data  

Describe the dataset the model uses.  

Prompts:  

- How many songs are in the catalog  
- What genres or moods are represented  
- Did you add or remove data  
- Are there parts of musical taste missing in the dataset  

The dataset used in this project contains 18 songs stored in a CSV file. Each song includes features such as title, artist, genre, mood, energy, tempo, valence, danceability, and acousticness.

The dataset includes a variety of genres and moods, such as pop, rock, and lofi, along with moods like chill, happy, and intense.

However, the dataset is very small and does not represent the full range of musical tastes. Some genres and moods are underrepresented, which limits the variety of recommendations the system can generate.

## 5. Strengths  

Where does your system seem to work well  

Prompts:  

- User types for which it gives reasonable results  
- Any patterns you think your scoring captures correctly  
- Cases where the recommendations matched your intuition  

The system works well for user profiles that closely match songs in the dataset. For example, the Chill Lofi profile produced very accurate results because the dataset included several songs with similar genre, mood, and energy levels.

The scoring system also successfully captures patterns between user preferences and song attributes. Songs that match both genre and mood tend to appear near the top of the recommendation list.

In several cases, the recommendations matched my intuition about what songs should appear for certain profiles.

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

If I continued improving this model, I would first expand the dataset to include more songs and genres. This would make the recommendations more diverse and realistic.

I would also include additional song features, such as valence and danceability, in the scoring system so the recommendations could capture more aspects of musical taste.

Another improvement would be allowing users to give feedback on recommendations so the system could learn and adjust its scoring over time.

## 9. Personal Reflection  

A few sentences about your experience.  

Prompts:  

- What you learned about recommender systems  
- Something unexpected or interesting you discovered  
- How this changed the way you think about music recommendation apps  

One of the biggest things I learned from this project is how even a simple scoring system can create recommendations that feel meaningful. By combining a few features like genre, mood, and energy, the system can produce results that seem personalized.

Something that surprised me was how much the scoring weights affected the results. When I increased the importance of energy, the same high-energy songs appeared across multiple profiles, showing how sensitive recommendation systems can be to small changes.

This project helped me better understand how music recommendation apps might work behind the scenes and how important data and feature selection are for building good recommendations.