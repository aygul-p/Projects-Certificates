**Project**: Spotify dataset (2015-2025)


**Source**: /kaggle/input/spotify-music-analytics-dataset-20152025/spotify_2015_2025_85k.csv


**Size**: 85k rows x 19 columns



**The Purpose of the EDA Analysis:**

- Explore structural patterns and distributions within a Spotify tracks dataset (2015–2025).
- Examine relationships between audio features, genres, popularity, and streaming behavior.
- Assess whether measurable musical attributes explain differences in popularity and streaming success.
- Identify signs of genre convergence, feature normalization, and platform-driven standardization.
- Evaluate data suitability and limitations for feature-based modeling and prediction.

**Tools** - 


- **Python**: 
- Pandas
- Matplotlib
- Seaborn
- **MySQL**  
- **Power BI**


**Structure**: 


- Data Cleaning and Statistics using Python
- Information Extraction with MySQL
- Data Visualization using Python & Power BI








**Data Cleaning with Python:**



- Missing values in track_name and album_name are replaced with 'Unknown Track' and 'Unknown Album'





  

  <img width="684" height="361" alt="image" src="https://github.com/user-attachments/assets/aab39d8c-e601-4989-b1e7-edb49c37b295" />







- Outliers in popularity (1806) and stream_count (14160) are detected but for this kind of dataset, outliers are important to extract precise information. Therefore, they remained unchanged.







  <img width="668" height="303" alt="image" src="https://github.com/user-attachments/assets/7cc21168-f369-4d61-a85f-cb704f567e2d" />






  <img width="659" height="278" alt="image" src="https://github.com/user-attachments/assets/586c5e53-42f0-401c-a467-77f2c9db4329" />








The duplicates were removed:










  <img width="310" height="209" alt="image" src="https://github.com/user-attachments/assets/fe65aa0d-2950-4535-9e9c-b41118df4e2d" />











**Statistics:**









- The model explains virtually none of the variation in tempo (R² ≈ 0), indicating that genre and year have negligible explanatory power over tempo at the track level.
- Although a few genre coefficients (e.g., Pop and Country) are statistically significant, their effect sizes are extremely small (≈ +1 BPM), making them practically insignificant.
- The year coefficient is not significant, confirming the absence of a meaningful temporal trend in tempo over time.
- The non-significant F-statistic indicates that, as a whole, the model does not meaningfully outperform a null model.
- Statistical significance is largely driven by the very large sample size (85k tracks) rather than substantive effects.
- High residual variance suggests that tempo variation is primarily driven by within-genre and track-level factors, not broad genre labels or release year.
- Overall, the results reinforce earlier findings: tempo differences exist descriptively across genres, but they are not strong enough to be predictive, highlighting structural stability rather than directional evolution in Spotify-era music.









<img width="702" height="574" alt="image" src="https://github.com/user-attachments/assets/2a3cf7bb-5654-4757-b521-6f1814f3ebe3" />










**MySQL**: 









1. **Danceability:** Spotify’s mainstream music has maintained a consistent rhythmic accessibility and danceability seems to be a mature, optimized trait rather than evolving, which suggests listeners’ preference for “movable” music hasn’t changed much in a decade.

**Energy:** Despite genre cycles among EDM, trap, pop, and hyperpop average perceived energy remains constant. Genre diversity cancels out extremes at scale, indicating that Spotify popularity favors balance, not extremes. 

**Loudness:** Streaming normalization is doing its job. Producers optimize for streaming rather than raw loudness, so this is strong evidence of platform-driven production behavior.

**Tempo:** Minimal variance across a decade is observed. About 130 BPM aligns with pop, dance, workout / driving playlists. This tempo range maximizes engagement, movement, and playlist compatibility. In short, Spotify’s ecosystem implicitly favors mid-high tempo music. 

**Key results:** 





- Spotify’s popular music ecosystem is highly optimized and stable
- Algorithms reward familiarity over experimentation
- Radical sonic shifts exist at genre level, not aggregate level
- Artists adapt to platform incentives subconsciously or strategically









<img width="685" height="587" alt="image" src="https://github.com/user-attachments/assets/f8438fa1-86b9-4920-a038-d2a19958e55c" />









2. - Tempo variability meaningfully differentiates genres, while energy variability remains tightly clustered.
   - Pop and Jazz show the highest tempo volatility, indicating rhythmic flexibility and cross-genre influence.
   - Classical, Country, and R&B exhibit more stable tempos, reflecting stronger structural traditions.
   - Energy variability differs only marginally across genres, suggesting platform-driven standardization.
   - Overall, genres in the Spotify era differentiate primarily through tempo, not energy, making rhythm the dominant axis of creative variation.









<img width="418" height="560" alt="image" src="https://github.com/user-attachments/assets/acb0fa39-dcf9-46ba-9af6-48cae691453e" />










3. - Average tempo, energy, and danceability remain tightly clustered across years and genres, indicating strong structural consistency in Spotify-era music.
   - Genres maintain distinct but stable tempo profiles, with Pop, EDM, and R&B generally exhibiting higher tempos than Classical or Jazz.
   - Energy levels vary only marginally between genres and across time, suggesting platform-driven normalization of intensity.
   - Danceability stays consistently moderate-to-high, reflecting prioritization of listener engagement and playlist compatibility.
   - Genre differentiation persists mainly through relative tempo differences, while energy and danceability show clear convergence.
   - Overall, the results point to a music ecosystem optimized for familiarity, algorithmic compatibility, and sustained engagement rather than radical sonic experimentation.










<img width="601" height="625" alt="image" src="https://github.com/user-attachments/assets/bb2042cf-5c0e-4d15-bd58-c1123d7cce24" />









4. - The artists with the highest track counts are dominated by very common names (e.g., Smith, Johnson, Brown), rather than globally recognizable Spotify artists.
   - This strongly suggests that artist names are anonymized, normalized, or synthetically generated, rather than representing real-world Spotify artist identities.
   - Track counts per artist are relatively low and tightly bounded (top ≈ 40 tracks), indicating the dataset is not popularity-driven and does not reflect true artist dominance.
   - The absence of well-known high-output artists implies the dataset is designed for structural and feature-level analysis, not market-share or fame analysis.
   - As a result, this table should not be interpreted as “top artists on Spotify”, but rather as a distribution of tracks across artist identifiers within a curated dataset.
   - Analytically, this setup is suitable for avoiding artist-level bias, ensuring no single artist disproportionately influences aggregate audio-feature trends.









<img width="488" height="623" alt="image" src="https://github.com/user-attachments/assets/5041b6e8-99df-4b3f-9d98-2fc3145484d2" />














**Python:**











1. - Average track popularity remains remarkably stable over time, fluctuating within a very narrow range.
   - Minor year-to-year changes are visible, but no sustained upward or downward trend emerges across the decade.
   - The temporary peak around 2021 appears short-lived and does not indicate a structural shift.
   - Overall stability suggests that Spotify’s popularity metric is normalized at scale, with new tracks continuously replacing older ones at similar average engagement levels.
   - These results imply that changes in musical characteristics (tempo, energy, genre) do not translate into large aggregate shifts in popularity over time.
   - Taken together with earlier analyses, this supports the conclusion that the Spotify ecosystem favors consistency and equilibrium, rather than long-term growth or decline in average popularity.












<img width="781" height="487" alt="image" src="https://github.com/user-attachments/assets/fcaca7f8-da69-421f-add0-9e21fffb789d" />











2. - All correlations between popularity and audio features (energy, danceability, loudness, tempo) are near zero, indicating no meaningful linear relationships.
   - This suggests that no single audio feature strongly drives popularity at the aggregate Spotify level.
   - Correlations among audio features themselves are also extremely weak, reinforcing the idea of independent feature optimization.
   - The absence of strong relationships implies that popularity is likely influenced by non-audio factors such as playlist placement, promotion, artist visibility, and algorithmic exposure.
   - These findings explain why earlier regression models show negligible explanatory power for tempo and popularity.
   - Overall, the heatmap supports the conclusion that Spotify popularity is structurally decoupled from basic audio characteristics, highlighting the limits of feature-only modeling.












  <img width="660" height="536" alt="image" src="https://github.com/user-attachments/assets/5744d8d0-9504-4c42-810d-834be6379a08" />













  3. - The scatter shows no visible linear or non-linear relationship between danceability and popularity.
     - Popularity values are widely dispersed across the entire danceability range, indicating that both low- and high-danceability tracks can be popular or unpopular.
     - The dense vertical spread reflects high variance in popularity at every danceability level, reinforcing weak predictive power.
     - This visual pattern is consistent with the near-zero correlation observed in the correlation matrix.
     - The results suggest that danceability alone is not a determining factor for Spotify popularity.
     - Popularity is likely driven by external and contextual factors (playlist placement, marketing, artist exposure) rather than isolated audio features.












  <img width="648" height="563" alt="image" src="https://github.com/user-attachments/assets/a603b2a8-d99e-4167-a779-90d6bd77a3b8" />







4. - The pairwise scatter plots show dense, uniform clouds with no visible linear or nonlinear relationships between audio features and popularity.
   - Danceability, energy, instrumentalness, and loudness appear largely independent, with minimal interaction patterns.
   - Popularity exhibits high variance across the full range of each audio feature, indicating that both low and high feature values can correspond to any popularity level.
   - The diagonal distributions confirm feature normalization and bounded ranges, consistent with Spotify’s standardized audio feature extraction.
   - Loudness shows a concentrated distribution, reflecting streaming-era mastering normalization, while popularity follows a roughly bell-shaped distribution due to platform scaling.
   - The absence of clear slopes or clusters reinforces earlier findings that basic audio features do not drive popularity in isolation.
   - Overall, this visualization supports the conclusion that Spotify success emerges from exposure dynamics rather than intrinsic audio characteristics, consistent with winner-takes-most behavior.







  <img width="1230" height="1231" alt="image" src="https://github.com/user-attachments/assets/55227196-ba81-4cd3-8e7b-d79f70af3b10" />






5. - The three clusters show heavy overlap in the energy–danceability space, with no clearly separable boundaries.
   - This indicates that tracks do not naturally segment into distinct groups based on these audio features alone.
   - The clusters primarily reflect density partitioning rather than meaningful behavioral or stylistic groupings.
   - The lack of separation suggests that energy and danceability are smoothly distributed, not clustered into discrete musical types.
   - This outcome aligns with earlier findings of feature convergence and normalization across Spotify-era music.
   - Overall, the results imply that unsupervised clustering on basic audio features provides limited interpretability, and richer features (e.g., genre, tempo volatility, popularity context) would be needed for meaningful segmentation.












<img width="648" height="555" alt="image" src="https://github.com/user-attachments/assets/d9c0e2b7-2617-47a6-9846-cc12be1ae7a8" />














6. - Tracks from all genres are densely intermingled across the danceability–energy space, with no clear genre-specific separation.
   - Bubble sizes (popularity) are evenly distributed, showing that highly popular tracks appear across a wide range of danceability and energy levels.
   - No visible pattern suggests that higher energy or higher danceability systematically leads to higher popularity.
   - Genre coloring reveals substantial overlap, indicating that genres share similar core audio profiles in the Spotify era.
   - This reinforces earlier findings that audio features alone do not explain popularity or genre dominance.
   - Overall, the plot highlights a highly homogenized feature space, where popularity is largely decoupled from basic musical attributes and more likely driven by external platform factors (e.g., playlists, exposure, marketing).













  <img width="1727" height="580" alt="image" src="https://github.com/user-attachments/assets/48de4383-1a3b-4471-9c7d-582c37c0a704" />













7. - The distribution of stream counts is highly right-skewed, even on a log scale, indicating extreme inequality in listening volume.
   - The vast majority of tracks accumulate relatively low stream counts, while a very small fraction achieve massively high streams.
   - This long-tail pattern is characteristic of a winner-takes-most distribution common in digital platforms.
   - The presence of a long right tail suggests that viral hits and playlist amplification drive disproportionate attention to a small subset of tracks.
   - Average or median stream counts therefore do not represent a “typical” track, making aggregation potentially misleading.
   - These results reinforce earlier findings that popularity and streams are driven more by exposure mechanisms than by audio features.
   - Overall, the Spotify ecosystem exhibits strong concentration of attention, where success is rare, unevenly distributed, and weakly tied to basic musical characteristics.
  











   <img width="591" height="497" alt="image" src="https://github.com/user-attachments/assets/baf5a116-95ef-4915-b00d-bb62dc752d5d" />











   8. - Average tempo remains remarkably stable from 2015 to 2025, fluctuating within a very narrow range (~129–131 BPM).
      - Year-to-year variations are minor and non-directional, with no sustained upward or downward trend.
      - The temporary dip around 2020 appears short-lived and does not indicate a structural shift in musical tempo.
      - This stability suggests that tempo has reached an engagement-optimized equilibrium in the Spotify ecosystem.
      - The results reinforce earlier findings that tempo differentiates genres descriptively, but shows little temporal evolution at the aggregate level.
      - Overall, the plot supports the conclusion that Spotify-era music prioritizes rhythmic consistency over innovation, aligning with platform-driven standardization.









     <img width="680" height="533" alt="image" src="https://github.com/user-attachments/assets/a54fedfa-8d8c-4e4f-9b62-00d912f5e026" />













**Power BI**: 












1. - The top-streamed tracks accumulate disproportionately high stream counts, reinforcing the winner-takes-most dynamics observed in the stream count distribution.
   - Track names themselves show no semantic or thematic pattern explaining high streams, suggesting success is not driven by naming or linguistic cues.
   - The artist popularity ranking is dominated by very common names (e.g., Smith, Johnson), indicating that artist identifiers are anonymized or synthetic, not real-world Spotify stars.
   - Popularity scores are relatively close in magnitude, with no extreme outliers, further supporting the idea of a normalized popularity metric.
   - These rankings should therefore not be interpreted as real market leaders, but as internal dataset aggregates.
   - Together, the charts reinforce a consistent narrative: streams and popularity are highly concentrated, but not meaningfully explained by track-level audio features or artist identity.
   - Overall, visibility and exposure mechanisms—rather than content attributes—appear to be the primary drivers of success in the Spotify ecosystem represented by this dataset.












   <img width="1103" height="497" alt="image" src="https://github.com/user-attachments/assets/4c42ffa9-4cf3-41a6-83c9-628f46499e14" />













2. - Stream count increases broadly with popularity, but the relationship is not perfectly linear, indicating diminishing returns at higher popularity levels.
   - Genres with similar popularity scores exhibit noticeably different stream volumes, suggesting that popularity alone does not fully explain streaming success.
   - Some genres achieve very high stream counts without being the most popular, highlighting the role of playlist reach, repeat listening, and genre-specific consumption habits.
   - The dispersion across genres shows that streaming intensity varies by genre, even when popularity is comparable.
   - This pattern reinforces earlier findings that streams and popularity capture related but distinct dimensions of success.
   - Overall, the chart suggests that exposure mechanics and listener behavior, rather than audio features or popularity scores alone, drive large differences in stream counts across genres.













  <img width="932" height="489" alt="image" src="https://github.com/user-attachments/assets/094c0133-2eaf-4504-aeb9-ee18aca758ae" />












  3. - Average danceability is nearly identical across all genres (~0.52), indicating strong convergence toward rhythmically accessible music.
     - Energy levels are also tightly clustered (~0.50–0.51), suggesting limited differentiation in intensity between genres.
     - Instrumentalness remains consistently low (~0.40) across genres, reflecting a dominance of vocal-centric tracks regardless of genre.
     - Traditional genre expectations (e.g., higher instrumentalness in Classical or Jazz) are not strongly reflected in the averages.
     - The minimal variation across genres highlights platform-driven standardization of core audio characteristics.
     - Overall, genres differ more in label and cultural identity than in measurable audio features, reinforcing the idea of a homogenized Spotify-era soundscape.
  











  
  <img width="905" height="524" alt="image" src="https://github.com/user-attachments/assets/55009850-ae99-4272-8132-332b0f44a499" />












4. - Average popularity remains broadly stable over time, fluctuating within a narrow band without a sustained upward or downward trend.
   - Short-term spikes and dips appear, but they do not persist, indicating no structural shift in popularity dynamics.
   - Danceability stays consistently high and flat across the entire time range, reinforcing long-term rhythmic standardization.
   - Energy levels are also stable, closely tracking danceability without notable divergence.
   - Temporal proximity (newer vs. older releases) does not meaningfully affect average popularity, suggesting recency alone is not a driver of success.
   - The alignment of popularity, danceability, and energy trends supports the conclusion that Spotify-era music is optimized for consistency rather than evolution.
   - Overall, release date explains very little variation in popularity or core audio features, reinforcing the dominance of platform exposure and listener behavior over musical attributes.














  <img width="1222" height="629" alt="image" src="https://github.com/user-attachments/assets/9a767ff0-0573-42f4-93a3-a7489f38b23e" />














5. - The number of tracks released over time remains relatively stable, with consistent counts across the entire 2015–2025 period.
   - Short-term fluctuations are present, but there is no sustained growth or decline, indicating a steady sampling or release rate.
   - Peaks and troughs appear irregular rather than seasonal, suggesting no strong calendar-driven release patterns.
   - The absence of structural breaks implies dataset consistency over time, with no years over- or under-represented.
   - This stability supports earlier findings that temporal effects have minimal influence on popularity and audio characteristics.
   - Overall, the chart indicates that observed trends are not driven by changes in data volume, strengthening the validity of prior analyses.













<img width="1032" height="602" alt="image" src="https://github.com/user-attachments/assets/5e3d966d-6751-4cef-8651-841ff5ddc650" />
















**Final Key Results:**









- Core audio features (danceability, energy, tempo, loudness) are highly stable across time and genres.
- Genre differentiation exists mainly through tempo, while energy and danceability converge.
- Correlation and regression analyses show no meaningful relationship between audio features and popularity.
- Average popularity remains stable over time, with no persistent temporal trends.
- Stream counts follow a highly skewed, long-tail distribution, with attention concentrated on a small fraction of tracks.
- Clustering on basic audio features produces overlapping groups, indicating a continuous feature space.
- This EDA shows that modern Spotify music is highly standardized in its audio characteristics, while popularity and streaming success are dominated by platform-driven exposure rather than measurable musical features.
- Overall, results suggest that platform exposure and algorithmic mechanisms, rather than audio characteristics, primarily drive popularity and streaming outcomes.



