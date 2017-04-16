---
layout: post
title:  "Tic Tac Toe and Scraping"
date:   2017-04-15 20:46:30 -0400
---


I finished up two projects today. I wasn't super enthused with the last couple of tic tac toes, so I was kind of dreading this one, but much to my surprise, it was SO FUN! Getting the tests to pass for the traditional methods took, some time and was tedious, but doing the AI portion was really fun. Here's the approach I took with coding the Computer class:

1. If middle is available, take it
2. If middle is not available, and it's your first turn, pick a corner. That's usually the best defense.
3. After you have at least 2 tokens on the table, loop through all the winning combinations, subtract the winning combo array from an array of all the indeces you have occupied. 
4. If you get to a combo that can be matched in one step, take the spot and win!
5. If not, play defense. See if your opponent can match any winning combos, and take that spot
6. Else, just pick something random that's still available.

I could've added a bit more strategy, but I decided that I had to move on.

Scraping was also very fun. I wish the CLI wasn't already written. It was helpful to read the code, but would have been more helpful to write it. 

My biggest challenge with this one was remember who to set and call hash keys/values.

Here's how you set:
```
hash = {:key => value}
```

Here's how you call
```
hash[:key] #=> value
```

Additionally, Nokogiri is great, but I keep forgeting how to use the css selectors, so here's a snippet as a reminder:
```
    student_array = []
    learn_student_page.css("div.student-card").each do |student|
      student = {
      :name => student.css("h4").text,
      :location => student.css("p").text,
      :profile_url => './fixtures/student-site/' + student.css("a").attribute("href").value
      }
      student_array << student
    end
```

Lastly, I didn't like the conditional scraping. There must be an easier way than what I implemented:

```
    social_media_links = learn_profile_page.css("div.social-icon-container a").map { |link| link['href'] }
    social_media_links.each do |link|
      if link.include?("twitter.com")
        student[:twitter] = link
      elsif link.include?("linkedin.com")
        student[:linkedin] = link
      elsif link.include?("github.com")
        student[:github] = link
      else
        student[:blog] = link
      end
    end
```

