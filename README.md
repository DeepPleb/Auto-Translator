# Auto-Translator
## Translate an audio and say it back in English

[Deepgram](deepgram.com) has a feature where it can automatically detect what language the speaker is speaking and transcibe the audio in that language. We can then use this transcript to translate the text into English and then use text to speech to save it into an audio file.

## Code

First we transcribe the text as we always do but by adding the `'detect_language': True` parameter.


Then we'll use google translate python sdk to translate the text into english. First we'll import google translate into our code.
(Make sure to pip3 install all packages before using)

`from googletrans import Translator, constants`

Later we can translate the text using:
  ```
  translator = Translator()
  translation = translator.translate(words)
  print(translation.text)
  ```
  
  Now that we have the translated text we will now use text to speech to save the audio to a . wav file
  We will be using pyttsx3 for this:
  
  `import pyttsx3`
  
 The default speed of the speech will be too low. So we will set the rate to 180
 
  ```
  engine = pyttsx3.init()
  engine.setProperty('rate', 180)
  ```

Finally we will save the new audio file:
  ```
  engine.save_to_file(translation.text, 'translated.wav')
  engine.runAndWait()
  ```
 
