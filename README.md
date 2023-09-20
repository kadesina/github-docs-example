# First Header

# github-docs-example



## References 

- [GitHub Flavored Markdown Spec](https://github.github.com/gfm/#links)

- [Github Flavored markDown](https://www.google.com/search?sca_esv=566704995&sxsrf=AM9HkKnqx3E5btAOGLZjZRHYA1bb3mZ-4w:1695156065585&q=Car&tbm=isch&source=lnms&sa=X&ved=2ahUKEwjwyoK5xLeBAxXOFVkFHdsKBLcQ0pQJegQIDBAB&biw=1854&bih=852&dpr=1)

- [Github Flavored MarkDown Emoji](https://gist.github.com/rxaviers/7360908)

- [Github table](https://github.github.com/gfm/#tables-extension-)
## Second Header 

```bash
#!/bin/bash

# Gmail API endpoint to fetch messages
API_URL="https://www.googleapis.com/gmail/v1/users/me/messages"

# Your Gmail API key
API_KEY="YOUR_API_KEY"

# Fetch the list of message IDs
message_ids=$(curl -s \
  -H "Authorization: Bearer $API_KEY" \
  "$API_URL?maxResults=10")

# Check if the request was successful
if [ $? -ne 0 ]; then
  echo "Failed to fetch emails."
  exit 1
fi

# Extract and display the list of message IDs
echo "Message IDs:"
echo "$message_ids" | jq '.messages[].id'

# Loop through the message IDs and fetch each email
for message_id in $(echo "$message_ids" | jq -r '.messages[].id'); do
  # Fetch the email using the message ID
  email=$(curl -s \
    -H "Authorization: Bearer $API_KEY" \
    "$API_URL/$message_id")

  # Display the email (you can customize this part)
  echo "Email:"
  echo "$email" | jq '.'
done

 ```

- [X] Finish Step 1
- [ ] Finish Step 2
- [ ] Finish Step 3

| Name | ShortCode |
| --- | --- |
| baz | bim |
