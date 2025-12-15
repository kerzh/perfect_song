# Chat Processing Prompt

Use this prompt to extract song ratings from chat exports:

---

Analyze temp.txt. It is a conversation between 3 people rating songs. One person always proposes the song (and it is assumed that they rate it at 10), the other two rate it between 1 and 10. They take turns.

The participants are:
- E = Evgenia
- M = Marcel  
- P = Patrick

temp.txt contains the latest conversation. Read it and extract information about all the songs (YouTube links) mentioned in the chat and the marks.

Make a JSON structure list that will be added to the songs.json based on this latest chat export. The format should be:

```json
{
  "id": [next_id],
  "date": "DD/MM/YYYY",
  "link": "https://youtu.be/...",
  "submitter": "E|M|P",
  "E": [rating_or_null],
  "M": [rating_or_null],
  "P": [rating_or_null]
}
```

Rules:
- The person who posts the link gets a rating of 10
- Extract ratings from messages like "5/10", "8/10", etc.
- If someone hasn't rated yet, use null
- Continue ID numbering from the last song in songs.json
- Date format is DD/MM/YYYY (extract from timestamps like [04/12/2025, 16:26:02])
