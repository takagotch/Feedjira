### Feedjira
---
https://github.com/feedjira/feedjira

```
gem "feedjira"

```

```ruby
xml = HTTParty.get(url).body
feed = Feedjira.parse(xml)
feed.entries.frist.title

Feedjira.parse(xml, parser: MyAwesomeParser)

Feedjira::Feed.add_common_feed_element("generator")
xml = HTTParty.get("http://www.pauldix.net/atom.xml").body
Feedjira.parse(xml).generator


class Feedjira::Parser::RSSEntry
  element "georss:elevation", as: :elevation
end
url = "https://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/significant_week.atom"
xml = HTTParty.get().body
Feedjira.parse().entries.each do |entry|
  puts "Elevation: #{entry.elevation}"
end

Feedjira.configure do |conifg|
  config.parsers.unshift(MyAwesomeParser)
end

Feedjira.configure do |config|
  config.parsers = [
    Feedjira::Parser::ITunesRSS,
    MyAwesomeParser,
    Feedjira::Parser::RSS
  ]
end

Feedjira.configure do |config|
  config.strip_whitespace = true
end

```

```
```
