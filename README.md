# hackathon-tips-and-tricks
Want to win a hackathon? Take a read through some helpful material, centered around IBM Cloud, to take you to victory!

# What's a Hackathon?
* "Hackathons provide a venue for self-expression and creativity through technology. People with technical backgrounds come together, form teams around a problem or idea, and collaboratively code a unique solution from scratch — these generally take shape in the form of websites, mobile apps, and robots.” ~ Open Savannah

* “A hackathon is a competitive event in which teams of designers, developers, and subject matter experts collaborate to create solutions for a specific problem within a defined time frame.” ~ hackerearth.com

* A weekend of collaborative coding (sometimes nonstop)

* Hack + Marathon = Hackathon

# 8 Basic Steps to Win a Hackathon
#### 1. Describe a business problem
Identify a problem that you think you can sovle. Choose something that you know is a pain point or a problem that your solution will solve.
#### 2. Tell a story about your solution
Make sure that you explain how your soluition is different from anything else out there and what benefit your solution has to the problem that you solved.
#### 3. Demo!
Show whatever you have, even if it's just a basic demo.

**Pro-tip: Always record a demo ahead of time incase you have an issue with the live demo so you can still show it!**
#### 4. Talk about your technology implementation
Explain the architecture behind your solution, what services or technologies you used, helpful libraries, etc
#### 5. Show the code, even if its a rough prototype
no matter how hacky your code might be, show it! It's always nice to see that you've written the code behind your solution.
#### 6. What you learned
Talk about the good and the bad that you've experienced as you went through putting something together!
#### 7. Why your solution to the business problem matters
Explain the value behind what you created. Why would people want to use this? What benefit could a person or business get from your solution?
#### 8. Next steps
Where can you take this idea next? What are some "stretch goals" or future ideas that you weren't able to squeeze into this first iteration?

# Useful Tools
Don't feel like setting up an enviroment for your hackathon? Wish you could just use something pre-built? Fear not! Here is a link to 2 pre-made containers that will get your there quickly. 

A container with the IBM CLI ready to go - https://github.com/derekteay/docker-ubuntu-ibm-cli

A container with 4 major runtimes (Python, Java, Node.js, and .NET Core) that is fully setup and ready to go - https://github.com/derekteay/docker-multi-runtime-container

# "Micro" Code Patterns
If you're not familiar with IBM Code Patterns, you can find them here: https://developer.ibm.com/patterns/

These patterns are great to get developers started with IBM technology, but sometimes, they're a little bit more than you need to get started. Below, I have setup a few "micro" code patterns that are the simplest way to setup a service and get you started in less than 3 minutes.

## Watson Text To Speech

For any of these to work, you need to create an IBM Cloud account (Click "Sign Up" in the top right) - https://www.ibm.com/cloud/

![IBM Cloud Registration](/screenshots/ibm-cloud-sign-up.png?raw=true "IBM Cloud Registration")

1. Create a Text to Speech service - https://console.bluemix.net/catalog/?category=ai

![Speech to Text Catalog](/screenshots/text-to-speech-catalog.png?raw=true "Speech to Text Catalog")

2. Use the default options and click "Create"

![Speech to Text Create](/screenshots/text-to-speech-create.png?raw=true "Speech to Text Create")

3. Get your credentials and use `curl` to turn your text into a wav file

![Text to Speech Credentials](/screenshots/text-to-speech-credentials.png?raw=true "Text to Speech Credentials")

```
curl -X POST -u "username":"password" \
--header "Content-Type: application/json" \
--header "Accept: audio/wav" \
--data '{"text": "hello world"}' \
--output hello_world.wav \
"https://stream.watsonplatform.net/text-to-speech/api/v1/synthesize"
```

Or an MP3 file

```
curl -X POST -u "username":"password" \
--header "Content-Type: application/json" \
--header "Accept: audio/mp3" \
--data '{"text": "hello world"}' \
--output hello_world.mp3 \
"https://stream.watsonplatform.net/text-to-speech/api/v1/synthesize"
```

## Watson Language Translator 

1. Create a Language Translator service - https://console.bluemix.net/catalog/?category=ai


![Language Translator Catalog](/screenshots/language-translator-catalog.png?raw=true "Language Translator Catalog")

2. Use the default options and click "Create"

![Language Translator Create](/screenshots/language-translator-create.png?raw=true "Language Translator Create")

3. Get your credentials and use `curl` to convert your text

![Language Translator Credentials](/screenshots/language-translator-credentials.png?raw=true "Language Translator Credentials")

```
curl --user apikey:secret-api-key \
--request POST \
--header "Content-Type: application/json" \
--data '{"text": ["Hello, world!"], "model_id":"en-es"}' \
https://gateway.watsonplatform.net/language-translator/api/v3/translate?version=2018-05-01
```

![Language Translator Output](/screenshots/language-translator-output.png?raw=true "Language Translator Output")
