import re

def detect_spam(comment):
# Define spam patterns using regular expressions
spam_patterns = [
r'\b(?:click\s*here|check\s*this\s*out)\b', r'\b(?:subscribe|subscribed|sub\s*back)\b', r'\b(?:great\s*video|awesome\s*content)\b', r'\b(?:follow\s*me|like\s*my\s*video)\b',
r'\b(?:make\s*money\s*online|earn\s*money)\b',
# Add more patterns as needed
]

# Check if the comment matches any spam pattern
for pattern in spam_patterns:
if re.search(pattern, comment, flags=re.IGNORECASE):
return True # Detected as spam

return False # Not detected as spam

if   name	 == "  main  ":
# Example comments
comments = [
"Great video! I really enjoyed it.",
"Check out my channel and subscribe!", "Earn money online, click here!",
"Nice content, I subscribed.", "This is not spam.",
]

# Check each comment for spam
for comment in comments:
if detect_spam(comment):
print(f"Spam detected: {comment}")
else:
print(f"Not spam: {comment}")
