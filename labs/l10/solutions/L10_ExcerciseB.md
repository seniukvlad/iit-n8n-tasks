The empty workflow
![alt text](image-6.png)

Jina HTTP Request node
![alt text](image-7.png)

Groq HTTP Request node
![alt text](image-8.png)
![alt text](image-9.png)
The body (Used as JavaScript object to fix some bugs): 
{{
{
  "model": "llama-3.3-70b-versatile",
  "temperature": 0.2,
  "messages": [
    {
      "role": "system",
      "content": "You are a helper that outputs ONLY valid JSON. Follow this schema: { \"title\": \"string\", \"summary_short\": \"string\", \"key_points\": [\"string\"], \"tags\": [\"string\"], \"source_url\": \"string\" }"
    },
    {
      "role": "user",
      "content": "Analyze this text: " + $json.data.substring(0, 10000)
    }
  ]
}
}}

The result of code
![alt text](image-10.png)