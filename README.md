# Web-Scarping
Steps for doing the projects: 
1.	Import necessary libraries: 
•	googleapiclient.discovery for interacting with the YouTube Data API
•	pandas for data manipulation
•	isodate for parsing video durations
•	datetime for working with dates and times

2.	Set channel name, published_after date, and API key 

3.	Defines several functions:

•	get_channel_id (channel_name): Retrieves the channel ID based on the provided channel name.
•	get_channel_info (channel_id): Fetches channel information, including statistics, description, and related playlist ID.
•	get_video_ids (youtube, playlist_id): Retrieves a list of video IDs from the specified playlist, filtered by the published_after date.
•	get_video_ids_final (youtube, video_ids): Further filters the video IDs based on the number of views and returns the final list.
•	get_average_duration (video_ids_final): Calculates the average duration of videos in minutes.
•	get_all_vidoes_info(video_ids_final): Fetches information about each video, including title, description, views, likes, comments, and tags.
•	get_comments_data(video_ids_final): Retrieves comments for each video, including the comment ID, text, date, likes, replies count, and author.
•	get_replies_data (video_ids_final): Fetches replies to comments for each video, including the reply ID, text, date, likes, and associated comment.

# Attention: The gender of channel presenter was impossible to retrieve since there was not any method to call it. Large datasets of names and associated genders can be used to train machine learning models to specify the gender of channel presenter. So, this column was removed in the channel_data table. 

## Attention: Based on YouTube documentation, "YouTube currently supports replies only for top-level comments. However, replies to replies may be supported in the future". So, # Replies of the reply was impossible to and it was removed Replies_data table.

4.	The script fetches the channel ID using the get_channel_id function and then retrieves the channel information using the get_channel_info function.

5.	The playlist ID is extracted from the channel information, and the script fetches the video IDs using the get_video_ids function.


6.	The script further filters the video IDs based on the number of views using the get_video_ids_final function.

7.	Creates four dataframes:
•	Channel_data: Combines the channel information and average duration.
•	Video_data: Contains information about each video.
•	Comment_data: Contains comments for each video.
•	Replies_data: Contains replies for each video.

8.	Save the dataframes as separate Excel files using the to_excel method.

