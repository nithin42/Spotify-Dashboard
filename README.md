

# Spotify Dashboard: Exploring Decades of Music Trends

### Dashboard Link : https://app.powerbi.com/links/gI0en102JU?ctid=e9b87214-8e8f-4ad0-90ec-9d5c56c94931&pbi_source=linkShare

## Problem Statement

This Spotify data dashboard provides comprehensive insights into music trends spanning from 1930 to 2023, aiding users in understanding track information and music attributes. By offering intuitive visualizations, including bar graphs and interactive menus for date and track selection, users can analyze average streams per year, track counts, and the percentage of minor tracks. The dashboard's primary goal is to equip music industry professionals and enthusiasts with actionable insights to comprehend evolving music consumption patterns and make informed decisions regarding strategic initiatives.


### PowerBi External tools
![Banner](https://github.com/nithin42/Spotify-Dashboard/assets/52503252/68b2ba68-be8f-4657-ae6b-6c3d97a48b30)

 



 DAX expression
       
       1) Max_stream = MAX('updated_file'[streams])
       2) top song streams = 
            CALCULATE(
                SUM('updated_file'[streams]),
                'updated_file'[streams]= MAX('updated_file'[streams])
            )
      3) Average stream Per year = 
            CALCULATE(
                AVERAGE('updated_file'[streams]),
                ALLEXCEPT('updated_file','Date'[Year]) 
            )
      4) top song vs avg = 
             VAR x =[top song vs avg val] RETURN
            
             IF(X >0,
             FORMAT(X, "#.0%") & " " & UNICHAR( 9650),
             FORMAT(X, "#.0%") & " " & UNICHAR( 9660)
             ) 
      5) top song vs avg val = 
            DIVIDE(
                [top song streams] - [Average stream Per year],
                [Average stream Per year]
            )
        


# Snapshot of Dashboard (Power BI Service)

![spotify dashbord](https://github.com/nithin42/Spotify-Dashboard/assets/52503252/fa76f303-9011-4286-81a0-fa96df38233f)


# Insights

**1) Track Information:** Explore a vast database of track names, artists, release dates, and the number of artists involved, facilitating trend analysis.<br><br>
**2) Music Attributes Analysis:** Gain insights into diverse music attributes such as acousticness, danceability, liveliness, speechiness, and valence to understand the characteristics of popular tracks and genres across different eras.<br><br>
**3) Stream Trends:** Visualize average streams per year to track the popularity of specific tracks or artists over time, enabling identification of emerging trends in music consumption.<br><br>
**4) Track Count Calendar:** View a calendar format representing the distribution of tracks over time, aiding in understanding the frequency of releases across different periods.<br><br>
**5) Percentage Analysis of Minor Tracks:** Analyze the percentage of minor tracks compared to the total, offering insights into the emotional tone of music over time.<br><br>
**6) Interactive Menu Options:** Utilize interactive menu options to filter data by date, year, track, and artist, providing a customizable and dynamic user experience.<br><br>
**7) Empowering Decision-Making:** Empower music industry professionals, researchers, and enthusiasts with actionable insights to inform decision-making, identify emerging talent, and understand cultural and artistic shifts shaping the industry.
