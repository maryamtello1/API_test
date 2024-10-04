Manual for Importing Your API Key

#### 1. **Python using `.env`**

**Steps:**
1. Install the `python-dotenv` package:
   ```bash
   pip install python-dotenv
   ```

2. Create a `.env` file:
   ```
   OPENAI_API_KEY=your-api-key-here
   ```

3. Use the `.env` in your Python script:
   ```python
   from dotenv import load_dotenv
   import os
   import openai

   load_dotenv()  # Load environment variables from .env
   openai.api_key = os.getenv("OPENAI_API_KEY")

   response = openai.Completion.create(
       model="gpt-4",
       prompt="Write a haiku about recursion in programming."
   )

   print(response.choices[0].text)
   ```

#### 2. **JavaScript using `.env`**

**Steps:**
1. Install `dotenv`:
   ```bash
   npm install dotenv
   ```

2. Create a `.env` file:
   ```
   OPENAI_API_KEY=your-api-key-here
   ```

3. Use the `.env` in your JavaScript code:
   ```javascript
   import dotenv from 'dotenv';
   import OpenAI from 'openai';

   dotenv.config();  // Load .env variables

   const openai = new OpenAI({
     apiKey: process.env.OPENAI_API_KEY,
   });

   const completion = await openai.chat.completions.create({
     model: "gpt-4o-mini",
     messages: [{ role: "system", content: "You are a helpful assistant." }]
   });

   console.log(completion.choices[0].message);
   ```

