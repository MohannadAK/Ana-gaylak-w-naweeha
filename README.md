# IEEEMDB System Design Documentation

## Table of Contents

- [[#1. Overview]]
- [[#2. Functional Requirements]]
- [[#3. Non-Functional Requirements]]
- [[#4. Data Model]]
- [[#5. API Design]]
- [[#6. High-Level Architecture]]
- [[#7. Deep Dives]]

## 1. Overview

IEEEMDB is a movie discovery and social platform that enables users to discover movies, track their viewing history, write reviews and share recommendations with their community.

## 2. Functional Requirements

### 2.1 Core User Features

**2.1.1 User Registration & Authentication**: Users can create accounts, login, and manage their profiles.
**2.1.2 Movie Search & Discovery:** Users can search for movies by title, actor, genre, or other parameters.
**2.1.3 Movie Information Display:** Display movie details including titles, descriptions, video trailers, cast members and genre.
**2.1.4 Rating & Review System:** Users can rate movies (1-5 stars) and write detailed text reviews.
**2.1.5 Personal Movie Lists:** Users can create custom lists (watchlist, favorites, "top 10 action movies", etc.).
**2.1.6 Watch History Tracking:** Automatic and manual tracking of movies users have watched.
**2.1.7 Movie Recommendations:** Personalized movie suggestions based on viewing history and preferences.

### 2.2 Administrative Features

**2.2.1 Movie Management**: Admins can add, edit and remove movies from the database.
**2.2.2 Content Management**: Admins can moderate user reviews and manage inappropriate content.
**2.2.2 User Management**: Admins can manage user accounts and handle reports.

### 2.3 System Features

**2.3.1 Notification System:** Push notifications for new releases, friend activity, and personalized recommendations.
**2.3.2 Advanced Filtering:** Filter movies by year, rating, genre combinations, availability on streaming platforms.

## 3. Non-Functional Requirements

**3.1 Scalability:** Support millions of users and movies with horizontal scaling capabilities.
**3.2 Performance:**

- Search results within 100ms for 95% of queries.
- Page load times under 2 seconds.
- Recommendation generation within 500ms.
**3.3 Availability:** 99.9% uptime with fault-tolerant design and disaster recovery.
**3.4 Security:**
- Secure  authentication and authorization.
- Data encryption at rest and in transit.
- Protection against common web vulnerabilities (XSS, CSRF, SSRF, etc.)
**3.5 User Experience:**
- Responsive design for mobile and desktop.
- Intuitive interface with fast search and discovery.
- Offline capability for previously viewed content.
  
## 4. Data Model

### 4.1 Core Entities

#### User Entity

      - user_id (Primary Key)
      - username (Unique)
      - email (Unique)
      - password_hash
      - profile_picture_url
      - bio
      - created_at
      - last_login

#### Movie Entity

      - movie_id (Primary Key)
      - title
      - original_title
      - release_date
      - runtime_minutes
      - poster_url
      - trailer_url
      - budget
      - imdb_rating
      - created_at
      - updated_at

#### Person Entity (Actors, Directors, etc.)

- person_id (Primary Key)
- name
- birth_date
- biography
- profile_image_url

#### Genre Entity

- genre_id (Primary Key)
- name (e.g., "Action", "Drama", "Comedy")

#### Review Entity

- review_id (Primary Key)
- user_id (Foreign Entity)
- movie_id (Foreign Key)
- rating (1 - 5)
- review_text
- created_at
- updated_at
- likes_count

# 5. API Design

## 6. High-Level Architecture

## 7. Deep Dives
