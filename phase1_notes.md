# Phase 1: Understanding the Problem (Step 1)

## 1) How Spotify, YouTube Music, and TikTok Predict What Users Like

These platforms use machine learning to predict what each user will likely enjoy next.  
They combine:
- **User behavior data** (likes, skips, watch/listen time, saves, shares, etc.)
- **Content data** (genre, tempo, mood, hashtags, captions, audio/video features)

### Spotify
- Uses a hybrid approach: collaborative filtering + content-based filtering + deep learning
- Learns from large-scale listening behavior
- Uses audio features and metadata
- Powers personalized playlists like Discover Weekly and Daily Mix

### YouTube Music
- Leverages YouTube’s broader recommendation system
- Uses listening/watch history, likes/skips, and search behavior
- Can include context signals (time, device, location if enabled)

### TikTok
- Recommends mainly through the For You feed
- Prioritizes engagement signals (watch time, completion, replays, likes, comments, shares)
- Uses content signals (captions, hashtags, sounds, visual features)

---

## 2) Collaborative Filtering vs Content-Based Filtering

### Collaborative Filtering
**Definition:** Recommends items based on behavior patterns across many users.

**How it works:**
- Finds users with similar behavior/taste
- Recommends songs/videos those similar users liked

**Example:**  
If Alice and Bob both like Songs A and B, and Bob also likes Song C, then Song C may be recommended to Alice.

**Pros:**
- Strong personalization
- Can surface unexpected discoveries

**Cons:**
- Cold-start problem for new users/items
- Needs interaction data to work well

### Content-Based Filtering
**Definition:** Recommends items with similar attributes to content a user already likes.

**How it works:**
- Compares item features (genre, tempo, mood, artist, etc.)
- Recommends “similar” songs/videos

**Pros:**
- Works better for new items
- Easier to explain

**Cons:**
- Can become repetitive
- Less likely to suggest very different content

---

## 3) Main Data Types Used in Recommendation Systems

### User-Behavior Data
- Likes/dislikes
- Skips
- Replays
- Listen/watch time
- Completion rate
- Playlist additions
- Search history
- Follows
- Shares/comments
- Recency and frequency of activity

### Content Features
- Genre
- Artist/album
- Tempo (BPM)
- Mood/valence
- Energy
- Danceability/acousticness/instrumentalness
- Language
- Release year/popularity
- Embeddings (learned numeric representations)

### Video-Specific Features (TikTok/YouTube)
- Captions
- Hashtags
- Sound used
- On-screen text
- Visual objects/scenes

---

## 4) Simple Recommendation Pipeline for a Music App

1. **Collect user interactions** (plays, likes, skips, saves, shares, watch/listen duration).
2. **Extract content features** for each song/video (genre, artist, tempo, mood, embeddings).
3. **Build user taste profiles** from behavior + feature preferences.
4. **Generate candidate recommendations**:
   - Collaborative candidates (from similar users)
   - Content-based candidates (from similar item attributes)
5. **Rank candidates** using a scoring model (preference match + recency + predicted engagement).
6. **Show top-N recommendations** in feed/playlist.
7. **Learn from feedback** and update continuously.

---

## Summary
Modern recommenders are usually **hybrid systems**.  
They combine collaborative filtering (crowd behavior patterns) with content-based filtering (item similarity), using both user interaction signals and item features to improve recommendations over time.