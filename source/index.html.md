---
title: Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://api.visionati.com'>Sign Up for an API Key</a>
  - <a href='https://github.com/visionati/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Visionati Content Analyzer

## Introduction

The [Visionati Content Analyzer](https://api.visionati.com/analyze) is a convenient app that quickly generates detailed descriptions, captions, and tags for your images and videos using multiple AI services. It can also check if content is NSFW, ensuring safe and appropriate usage. Designed for efficiency and accuracy, Visionati transforms your content management process with advanced AI capabilities. The app works seamlessly on both mobile and desktop, integrating effortlessly with your phone camera for a smooth user experience.

![Visionati Content Analyzer](https://visionati.com/_assets/img/analyze.webp)

## AI Backends

You can select the exact AI services you want to use to analyze your images and videos by visiting your profile edit page!

This will allow you to pick and choose from a variety of AI services, including:

- [BakLLaVa](https://replicate.com/lucataco/bakllava)
- [Claude*](https://claude.ai/)
- [Gemini*](https://gemini.google.com/)
- [Grok*](https://x.ai/)
- [Jina AI](https://jina.ai/)
- [LLaVA](https://replicate.com/yorickvp/llava-13b)
- [OpenAI*](https://openai.com/)
- [Clarifai*](https://www.clarifai.com/)
- [Google Vision*](https://cloud.google.com/vision)
- [Imagga](https://imagga.com/)
- [Rekognition*](https://aws.amazon.com/rekognition/)

\* Recommended services which provide the best results with the fastest response times.

## Roles

Visionati's Content Analyzer offers flexible role-based functionality, allowing you to choose from predefined roles or create your own prompts to tailor content analysis. The default roles include:

- Artist: Provides an artistic take on the image.
- Caption: Generates a short, concise caption.
- Comedian: Delivers a humorous description.
- Critic: Offers a detailed critical analysis.
- General: The default role for general descriptions.
- Ecommerce: Creates product descriptions for online stores.
- Inspector: Provides the most detailed, thorough inspection.
- Promoter: Helps event promoters market the contents of an image.
- Prompt: Generates prompts to recreate the image in services like Midjourney.
- Realtor: Produces real estate descriptions.
- Tweet: Crafts a tweet about the image.

These roles enable precise and context-specific image interpretations, enhancing the usability of Visionati for various applications.

## Usage

Using the Visionati Content Analyzer is straightforward and efficient. Follow these steps:

1. **Upload Image or Video**: Open the app and upload your image or video using the file upload option, enter a URL, or take a new photo or video with your phone camera.
2. **Select Role**: Choose a predefined role from the dropdown menu or input your own custom prompt for tailored analysis.
3. **Analyze**: Click the 'Submit' button to process the content. The app will generate detailed descriptions, captions, and tags based on your selected role.
4. **Review Results**: Review the generated content and check for NSFW warnings.
5. **Copy or Share**: Copy the analyzed content to the clipboard or share it directly on X (formerly Twitter).

# Visionati API

## Introduction

The Visionati API is used to analyze images and videos. You can fetch a variety of data including tags, descriptions, faces, brands, colors, and text. You can even scan YouTube, Vimeo and X videos!

The API runs on credits. Each image or frame of video requires 1-6 credits depending on the features and backends you request, that way simple queries are less expensive. You can easily buy additional credits at our [API server](https://api.visionati.com).

For simple requests, for instance tags and nsfw, it would cost 1 credit. However, if you wanted every feature and backend activated, it would cost 6 credits.

## Authentication

> To authorize, use this code:

```shell
# You need to pass the correct header with each request.
curl "<API_ENDPOINT>"
  -H "X-API-Key: Token <YOUR_API_KEY>"
```

> Make sure to replace `<YOUR_API_KEY>` with your API key.

Visionati uses API keys to allow access to the API. You can register an account at our [API server](https://api.visionati.com).

Visionati expects for the API key to be included in all API requests to the server in a header that looks like the following:

`X-API-Key: Token <YOUR_API_KEY>`

Older apps may be using the `Authorization` header. This is now deprecated to improve compatibility with CORS.

`Authorization: Token <YOUR_API_KEY>`

<aside class="notice">
You must replace <code>&lt;YOUR_API_KEY&gt;</code> with your API key.
</aside>

## Analyze an Image/Video

```shell
# Sample call to analyze an image.
curl "https://api.visionati.com/api/fetch?url=https%3A%2F%2Fthoughts.greyh.at%2Fposts%2Fbreathe%2Fimages%2Fcover.webp"
  -H "X-API-Key: Token <YOUR_API_KEY>"
```

> The command above returns the following JSON. The second response below is returned if you request multiple images/videos.

```json
{
  "request_id":"5ec7ecc6-8a61-417b-b7bb-1aa00b9ed7a7",
  "user_id":1,
  "urls":[
    "https://thoughts.greyh.at/posts/breathe/images/cover.webp"
  ],
  "files": 0,
  "file_names": [],
  "features": [],
  "backends": [],
  "role": "general",
  "tag_score": 0.85,
  "capture_interval": 0,
  "max_frames": 3,
  "credits_paid": 3,
  "credits": 1209,
    "all": {
    "assets": [
      {
        "name": "https://thoughts.greyh.at/posts/breathe/images/cover.webp",
        "tags": {
          "Buddha": [
            {
              "name": "Buddha",
              "score": 0.9547365,
              "source": "clarifai"
            }
          ],
          "ancient": [
            {
              "name": "ancient",
              "score": 0.907019,
              "source": "clarifai"
            }
          ],
          "architecture": [
            {
              "name": "architecture",
              "score": 0.9429848,
              "source": "clarifai"
            }
          ],
          "art": [
            {
              "name": "art",
              "score": 0.97909284,
              "source": "clarifai"
            },
            {
              "name": "art",
              "score": 0.8106541,
              "source": "googlevision"
            }
          ],
          "building": [
            {
              "name": "building",
              "score": 0.8676134,
              "source": "googlevision"
            }
          ],
          "church": [
            {
              "name": "church",
              "score": 0.97136486,
              "source": "clarifai"
            }
          ],
          "culture": [
            {
              "name": "culture",
              "score": 0.9410028,
              "source": "clarifai"
            }
          ],
          "decoration": [
            {
              "name": "decoration",
              "score": 0.89900476,
              "source": "clarifai"
            }
          ],
          "god": [
            {
              "name": "god",
              "score": 0.90626276,
              "source": "clarifai"
            }
          ],
          "gold": [
            {
              "name": "gold",
              "score": 0.9167078,
              "source": "clarifai"
            }
          ],
          "landmark": [
            {
              "name": "landmark",
              "score": 0.7805456,
              "source": "googlevision"
            }
          ],
          "leisure": [
            {
              "name": "leisure",
              "score": 0.7397186,
              "source": "googlevision"
            }
          ],
          "meditation": [
            {
              "name": "meditation",
              "score": 0.7004138,
              "source": "googlevision"
            }
          ],
          "no person": [
            {
              "name": "no person",
              "score": 0.9178982,
              "source": "clarifai"
            }
          ],
          "old": [
            {
              "name": "old",
              "score": 0.9413237,
              "source": "clarifai"
            }
          ],
          "plant": [
            {
              "name": "plant",
              "score": 0.90841097,
              "source": "googlevision"
            }
          ],
          "religion": [
            {
              "name": "religion",
              "score": 0.9888678,
              "source": "clarifai"
            }
          ],
          "religious": [
            {
              "name": "religious",
              "score": 0.8962641,
              "source": "clarifai"
            }
          ],
          "sculpture": [
            {
              "name": "sculpture",
              "score": 0.9821177,
              "source": "clarifai"
            },
            {
              "name": "sculpture",
              "score": 0.8460582,
              "source": "googlevision"
            }
          ],
          "spirituality": [
            {
              "name": "spirituality",
              "score": 0.906218,
              "source": "clarifai"
            }
          ],
          "statue": [
            {
              "name": "statue",
              "score": 0.9778216,
              "source": "clarifai"
            },
            {
              "name": "statue",
              "score": 0.8353917,
              "source": "googlevision"
            }
          ],
          "symbol": [
            {
              "name": "symbol",
              "score": 0.89317465,
              "source": "clarifai"
            }
          ],
          "temple": [
            {
              "name": "temple",
              "score": 0.97307837,
              "source": "clarifai"
            },
            {
              "name": "temple",
              "score": 0.7803701,
              "source": "googlevision"
            }
          ],
          "traditional": [
            {
              "name": "traditional",
              "score": 0.8843783,
              "source": "clarifai"
            }
          ],
          "travel": [
            {
              "name": "travel",
              "score": 0.96362764,
              "source": "clarifai"
            }
          ]
        },
        "colors": {
          "#363333": [
            {
              "hex": "#363333",
              "score": 0.014964638,
              "pixel_fraction": 0.21169269,
              "red": 54,
              "green": 51,
              "blue": 51,
              "source": "googlevision"
            }
          ],
          "#54504e": [
            {
              "hex": "#54504e",
              "score": 0.007167647,
              "pixel_fraction": 0.18531026,
              "red": 84,
              "green": 80,
              "blue": 78,
              "source": "googlevision"
            }
          ],
          "#695541": [
            {
              "hex": "#695541",
              "score": 0.0076295147,
              "pixel_fraction": 0.028493036,
              "red": 105,
              "green": 85,
              "blue": 65,
              "source": "googlevision"
            }
          ],
          "#79533d": [
            {
              "hex": "#79533d",
              "score": 0.041782755,
              "pixel_fraction": 0.017095821,
              "red": 121,
              "green": 83,
              "blue": 61,
              "source": "googlevision"
            }
          ],
          "#90775f": [
            {
              "hex": "#90775f",
              "score": 0.045921545,
              "pixel_fraction": 0.044674266,
              "red": 144,
              "green": 119,
              "blue": 95,
              "source": "googlevision"
            }
          ],
          "#9c735a": [
            {
              "hex": "#9c735a",
              "score": 0.42039907,
              "pixel_fraction": 0.0764739,
              "red": 156,
              "green": 115,
              "blue": 90,
              "source": "googlevision"
            }
          ],
          "#a4734f": [
            {
              "hex": "#a4734f",
              "score": 0.049462765,
              "pixel_fraction": 0.006894611,
              "red": 164,
              "green": 115,
              "blue": 79,
              "source": "googlevision"
            }
          ],
          "#b09377": [
            {
              "hex": "#b09377",
              "score": 0.04548987,
              "pixel_fraction": 0.017095821,
              "red": 176,
              "green": 147,
              "blue": 119,
              "source": "googlevision"
            }
          ],
          "#b58b70": [
            {
              "hex": "#b58b70",
              "score": 0.2676177,
              "pixel_fraction": 0.04052343,
              "red": 181,
              "green": 139,
              "blue": 112,
              "source": "googlevision"
            }
          ],
          "#b8875e": [
            {
              "hex": "#b8875e",
              "score": 0.056730855,
              "pixel_fraction": 0.0052061346,
              "red": 184,
              "green": 135,
              "blue": 94,
              "source": "googlevision"
            }
          ]
        },
        "nsfw": [
          {
            "label": "sfw",
            "score": 0.98024684,
            "source": "clarifai"
          },
          {
            "label": "nsfw",
            "score": 0.019753128,
            "source": "clarifai"
          },
          {
            "label": "adult",
            "likelihood": "UNLIKELY",
            "source": "googlevision"
          },
          {
            "label": "violence",
            "likelihood": "UNLIKELY",
            "source": "googlevision"
          },
          {
            "label": "spoof",
            "likelihood": "VERY_UNLIKELY",
            "source": "googlevision"
          },
          {
            "label": "medical",
            "likelihood": "UNLIKELY",
            "source": "googlevision"
          }
        ],
        "descriptions":[
          {
            "description":"This image captures a serene representation of a Buddha statue seated in the lotus position, cradled within an intricately carved wooden mandorla. The mandorla with its flame-like patterning radiates out from the statue, symbolizing spiritual radiance and enlightenment. The Buddha is depicted with a gentle smile and eyes lowered in meditative introspection. Above, a complex, dark wooden ceiling structure lends an imposing architectural dimension, contributing to the sense of tranquility and sanctity in this space. Foreground floral offerings add vibrant color, suggesting ongoing veneration and cultural significance. The photo conveys a combination of artistry, spirituality, and the calm ambiance of a sacred place.",
            "source": "openai"
          }
        ]
      }
    ],
    "errors":[
      "failed to decode image: image: unknown format",
      "Unexpected error while running the classification job."
    ]
  }
}
```

> Response if you sent a batch request.

```json
{
  "request_id": "267f99ce-c797-4855-807f-21b204edb7ed",
  "user_id": 1,
  "urls": ["https://i.imgur.com/XUXe335.jpg", "https://media.treehugger.com/assets/images/2016/07/green-forest-trees.jpg.860x0_q70_crop-scale.jpg"],
  "files": 0,
  "file_names": [],
  "features": [],
  "backends": [],
  "role": "general",
  "tag_score": 0.8,
  "capture_interval": 0,
  "max_frames": 3,
  "success": true,
  "response_uri": "https://api.visionati.com/api/response/267f99ce-c797-4855-807f-21b204edb7ed"
}
```

This is the main endpoint of the API, and is used to analyze an image or video. If you pass it multiple images/videos to scan then it will provide a different response with a `response_uri` to poll for results.

### HTTP Request

`GET/POST https://api.visionati.com/api/fetch`

### Query Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
url | false | none | URL to the image/video you wish to scan. Videos return an async response.
url[] | false | none | URLs to the images/videos you wish to analyze. This param should be passed multiple times. Returns an async response.
file | false | none | Base64 value or Data URI of the image/video file. Returns an async response.
file[] | false | none | Base64 value or Data URI for each image/video file. This param should be passed multiple times. Returns an async response.
file_name | false | none | Uploaded file name.
file_name[] | false | none | Uploaded file names. This param should be passed multiple times.
backend | false | all | Select a single backend you want to enable. Valid values are: clarifai, imagga, googlevision, rekognition, llava, bakllava, jinaai, gemini, claude, grok and openai. By default clarifai, imagga, googlevision, rekognition, gemini, claude, grok and openai are all enabled.
backend[] | false | all | Allows you to pass multiple backends at the same time. That way you can just enable openai and googlevision if you want. Note, the response time could be lengthy if you have all backends enabled.
feature | false | all | Select features you want to enable. By default all features are enabled. Valid values are: brands, colors, descriptions, faces, nsfw, tags, and texts.
feature[] | false | all | Allows you to pass multiple features at the same time. That way you can just scan tags and faces if you want.
role | false | general | Pick the role, or persona for your description. This allows for more customized descriptions! Valid values are: artist, caption, comedian, critic, general, ecommerce, inspector, promoter, prompt, realtor, and tweet.
language | false | English | Set the language returned for all descriptions. Valid values are: Abkhazian, Afar, Afrikaans, Albanian, Amharic, Arabic, Aragonese, Armenian, Assamese, Aymara, Azerbaijani, Bashkir, Basque, Bengali (Bangla), Bhutani, Bihari, Bislama, Breton, Bulgarian, Burmese, Byelorussian (Belarusian), Cambodian, Catalan, Cherokee, Chewa, Chinese, Chinese (Simplified), Chinese (Traditional), Corsican, Croatian, Czech, Danish, Divehi, Dutch, Edo, English, Esperanto, Estonian, Faeroese, Farsi, Fiji, Finnish, French, Frisian, Fulfulde, Galician, Gaelic (Scottish), Gaelic (Manx), Georgian, German, Greek, Greenlandic, Guarani, Gujarati, Haitian Creole, Hausa, Hawaiian, Hebrew, Hindi, Hungarian, Icelandic, Ido, Igbo, Indonesian, Interlingua, Interlingue, Inuktitut, Inupiak, Irish, Italian, Japanese, Javanese, Kannada, Kanuri, Kashmiri, Kazakh, Kinyarwanda (Ruanda), Kirghiz, Kirundi (Rundi), Konkani, Korean, Kurdish, Laothian, Latin, Latvian (Lettish), Limburgish (Limburger), Lingala, Lithuanian, Macedonian, Malagasy, Malay, Malayalam, Maltese, Maori, Marathi, Moldavian, Mongolian, Nauru, Nepali, Norwegian, Occitan, Oriya, Oromo (Afaan Oromo), Papiamentu, Pashto (Pushto), Polish, Portuguese, Punjabi, Quechua, Rhaeto-Romance, Romanian, Russian, Samoan, Sangro, Sanskrit, Serbian, Serbo-Croatian, Sesotho, Setswana, Shona, Sichuan Yi, Sindhi, Sinhalese, Siswati, Slovak, Slovenian, Somali, Spanish, Sundanese, Swahili (Kiswahili), Swedish, Syriac, Tagalog, Tajik, Tamazight, Tamil, Tatar, Telugu, Thai, Tibetan, Tigrinya, Tonga, Tsonga, Turkish, Turkmen, Twi, Uighur, Ukrainian, Urdu, Uzbek, Venda, Vietnamese, Volapük, Wallon, Welsh, Wolof, Xhosa, Yiddish yi, Yoruba, and Zulu
prompt | false | none | Text prompt to use when generating a description. Takes priority over role.
tag_score | false | 0.9 | Minimum tag score for the results. Valid values are floats between 0 and 1.
capture_interval | false | 1 | The time in seconds between video image captures. By default videos process every second. Valid values are integers greater than 0.
max_frames | false | 3 | By default videos process every frame. This allows you to set the max number of frames to process. To remove the limit, set this value to 0.

You can also POST to the `/api/fetch` endpoint with JSON. Here is a sample payload:

`{
  "feature": ["nsfw", "tags", "descriptions"],
  "role": "general",
  "url": [
    "https://example.com/info.png",
    "https://example.com/second.png"
  ]
}`

When dealing with files, we recommend using POST requests.

<aside class="success">
Remember - anytime you see a param that ends in [], you can use it multiple times!
</aside>

## Async Response

```shell
curl "https://api.visionati.com/api/response/267f99ce-c797-4855-807f-21b204edb7ed"
  -H "X-API-Key: Token <YOUR_API_KEY>"
```

> The command above returns the following JSON as it is processing. The second response below is returned if processing is complete.

```json
{
  "request_id": "267f99ce-c797-4855-807f-21b204edb7ed",
  "user_id": 1,
  "urls": ["https://i.imgur.com/XUXe335.jpg", "https://media.treehugger.com/assets/images/2016/07/green-forest-trees.jpg.860x0_q70_crop-scale.jpg"],
  "files": 0,
  "file_names": [],
  "features": [],
  "backends": [],
  "role": "general",
  "tag_score": 0.8,
  "capture_interval": 0,
  "max_frames": 3,
  "status": "processing"
}
```

> Response when processing is complete.

```json
{
  "request_id": "267f99ce-c797-4855-807f-21b204edb7ed",
  "user_id": 1,
  "urls": ["https://i.imgur.com/XUXe335.jpg", "https://media.treehugger.com/assets/images/2016/07/green-forest-trees.jpg.860x0_q70_crop-scale.jpg"],
  "files": 0,
  "file_names": [],
  "features": [],
  "backends": [],
  "role": "general",
  "tag_score": 0.8,
  "capture_interval": 0,
  "max_frames": 3,
  "credits": 856,
  "credits_paid": 2,
  "all": {
    "assets": [{
      "name": "https://i.imgur.com/XUXe335.jpg",
      "tags": {
        "Historic site": [{
          "name": "Historic site",
          "score": 0.8550074
        }],
        "Sand": [{
          "name": "Sand",
          "score": 0.95072967
        }],
        "ancient": [{
          "name": "ancient",
          "score": 0.96067786
        }],
        "antique": [{
          "name": "antique",
          "score": 0.95298517
        }],
        "archaeology": [{
          "name": "archaeology",
          "score": 0.8163238
        }],
        "architecture": [{
          "name": "architecture",
          "score": 0.90563744
        }],
        "art": [{
          "name": "art",
          "score": 0.8780494
        }],
        "beige color": [{
          "name": "beige color",
          "score": 0.983
        }],
        "desert": [{
          "name": "desert",
          "score": 0.83813953
        }],
        "measuring instrument": [{
          "name": "measuring instrument",
          "score": 0.841
        }],
        "nature": [{
          "name": "nature",
          "score": 0.83924955
        }],
        "no person": [{
          "name": "no person",
          "score": 0.9846246
        }],
        "old": [{
          "name": "old",
          "score": 0.95872563
        }],
        "outdoors": [{
          "name": "outdoors",
          "score": 0.9428955
        }],
        "retro": [{
          "name": "retro",
          "score": 0.91253495
        }],
        "sand": [{
          "name": "sand",
          "score": 0.8890777
        }],
        "sky": [{
          "name": "sky",
          "score": 0.840596
        }],
        "stone": [{
          "name": "stone",
          "score": 0.8253684
        }],
        "sundial": [{
          "name": "sundial",
          "score": 0.841
        }, {
          "name": "sundial",
          "score": 1
        }],
        "timepiece": [{
          "name": "timepiece",
          "score": 0.841
        }, {
          "name": "timepiece",
          "score": 0.8663619232177731
        }],
        "traditional": [{
          "name": "traditional",
          "score": 0.86968356
        }],
        "travel": [{
          "name": "travel",
          "score": 0.95432603
        }]
      },
      "colors": {
        "#512d16": [{
          "hex": "#512d16",
          "score": 0.05418332,
          "pixel_fraction": 0.054410838,
          "red": 81,
          "green": 45,
          "blue": 22
        }],
        "#587b96": [{
          "hex": "#587b96",
          "score": 0.021196907,
          "pixel_fraction": 0.009814613,
          "red": 88,
          "green": 123,
          "blue": 150
        }],
        "#63a6f6": [{
          "hex": "#63a6f6",
          "score": 0.12261884,
          "pixel_fraction": 0.10709981,
          "red": 99,
          "green": 166,
          "blue": 246
        }],
        "#6ca5e3": [{
          "hex": "#6ca5e3",
          "score": 0.063343495,
          "pixel_fraction": 0.03403547,
          "red": 108,
          "green": 165,
          "blue": 227
        }],
        "#714b30": [{
          "hex": "#714b30",
          "score": 0.044825763,
          "pixel_fraction": 0.04895827,
          "red": 113,
          "green": 75,
          "blue": 48
        }],
        "#976c46": [{
          "hex": "#976c46",
          "score": 0.04776877,
          "pixel_fraction": 0.049589623,
          "red": 151,
          "green": 108,
          "blue": 70
        }],
        "#987253": [{
          "hex": "#987253",
          "score": 0.07415027,
          "pixel_fraction": 0.058313724,
          "red": 152,
          "green": 114,
          "blue": 83
        }],
        "#b29474": [{
          "hex": "#b29474",
          "score": 0.07692947,
          "pixel_fraction": 0.05647707,
          "red": 178,
          "green": 148,
          "blue": 116
        }],
        "#b68f6e": [{
          "hex": "#b68f6e",
          "score": 0.05362947,
          "pixel_fraction": 0.061527867,
          "red": 182,
          "green": 143,
          "blue": 110
        }],
        "#debe9a": [{
          "hex": "#debe9a",
          "score": 0.053562753,
          "pixel_fraction": 0.11892326,
          "red": 222,
          "green": 190,
          "blue": 154
        }]
      },
      "texts": [{
        "bounding_poly": {
          "vertices": [{
            "x": 145,
            "y": 16
          }, {
            "x": 395,
            "y": 16
          }, {
            "x": 395,
            "y": 33
          }, {
            "x": 145,
            "y": 33
          }]
        },
        "text": "Stargate sand sculpture...\n"
      }, {
        "bounding_poly": {
          "vertices": [{
            "x": 145,
            "y": 16
          }, {
            "x": 233,
            "y": 16
          }, {
            "x": 233,
            "y": 33
          }, {
            "x": 145,
            "y": 33
          }]
        },
        "text": "Stargate"
      }, {
        "bounding_poly": {
          "vertices": [{
            "x": 234,
            "y": 16
          }, {
            "x": 279,
            "y": 16
          }, {
            "x": 279,
            "y": 32
          }, {
            "x": 234,
            "y": 32
          }]
        },
        "text": "sand"
      }, {
        "bounding_poly": {
          "vertices": [{
            "x": 283,
            "y": 16
          }, {
            "x": 395,
            "y": 16
          }, {
            "x": 395,
            "y": 33
          }, {
            "x": 283,
            "y": 33
          }]
        },
        "text": "sculpture..."
      }],
      "nsfw": [{
        "label": "sfw",
        "score": 0.9995708
      }, {
        "label": "nsfw",
        "score": 0.00042922708
      }, {
        "label": "adult",
        "likelihood": "VERY_UNLIKELY"
      }, {
        "label": "violence",
        "likelihood": "VERY_UNLIKELY"
      }, {
        "label": "spoof",
        "likelihood": "VERY_UNLIKELY"
      }, {
        "label": "medical",
        "likelihood": "VERY_UNLIKELY"
      }, {
        "label": "safe",
        "score": 0.9854914093017579
      }, {
        "label": "underwear",
        "score": 0.0130350482463837
      }],
      "brands": {
        "eagleburgmann": [{
          "name": "eagleburgmann",
          "score": 0.8401
        }]
      }
    }, {
      "name": "https://media.treehugger.com/assets/images/2016/07/green-forest-trees.jpg.860x0_q70_crop-scale.jpg",
      "tags": {
        "Forest": [{
          "name": "Forest",
          "score": 0.9892672
        }],
        "Green": [{
          "name": "Green",
          "score": 0.9679495
        }],
        "Natural environment": [{
          "name": "Natural environment",
          "score": 0.9783299
        }],
        "Natural landscape": [{
          "name": "Natural landscape",
          "score": 0.9851578
        }],
        "Nature": [{
          "name": "Nature",
          "score": 0.97681445
        }],
        "Nature reserve": [{
          "name": "Nature reserve",
          "score": 0.9639079
        }],
        "Old-growth forest": [{
          "name": "Old-growth forest",
          "score": 0.9698044
        }],
        "Tree": [{
          "name": "Tree",
          "score": 0.9944205
        }],
        "Tropical and subtropical coniferous forests": [{
          "name": "Tropical and subtropical coniferous forests",
          "score": 0.97010356
        }],
        "Woodland": [{
          "name": "Woodland",
          "score": 0.9837558
        }],
        "dawn": [{
          "name": "dawn",
          "score": 0.96872115
        }],
        "daylight": [{
          "name": "daylight",
          "score": 0.88768035
        }],
        "environment": [{
          "name": "environment",
          "score": 0.9598845
        }],
        "fair weather": [{
          "name": "fair weather",
          "score": 0.956573
        }],
        "fall": [{
          "name": "fall",
          "score": 0.90823317
        }],
        "forest": [{
          "name": "forest",
          "score": 0.8639950561523441
        }],
        "growth": [{
          "name": "growth",
          "score": 0.91593105
        }],
        "guidance": [{
          "name": "guidance",
          "score": 0.9471642
        }],
        "landscape": [{
          "name": "landscape",
          "score": 0.9808681
        }],
        "leaf": [{
          "name": "leaf",
          "score": 0.98558354
        }],
        "lush": [{
          "name": "lush",
          "score": 0.9471315
        }],
        "mist": [{
          "name": "mist",
          "score": 0.9281504
        }],
        "nature": [{
          "name": "nature",
          "score": 0.9820632
        }],
        "no person": [{
          "name": "no person",
          "score": 0.9591023
        }],
        "park": [{
          "name": "park",
          "score": 0.9507468
        }],
        "scenic": [{
          "name": "scenic",
          "score": 0.9073466
        }],
        "southern beech": [{
          "name": "southern beech",
          "score": 0.879313430786133
        }],
        "sun": [{
          "name": "sun",
          "score": 0.954275
        }],
        "sunbeam": [{
          "name": "sunbeam",
          "score": 0.966048
        }],
        "tree": [{
          "name": "tree",
          "score": 0.97798496
        }, {
          "name": "tree",
          "score": 1
        }],
        "trunk": [{
          "name": "trunk",
          "score": 0.8971928
        }],
        "wood": [{
          "name": "wood",
          "score": 0.99636936
        }],
        "woody plant": [{
          "name": "woody plant",
          "score": 0.8354441070556641
        }]
      },
      "colors": {
        "#090d02": [{
          "hex": "#090d02",
          "score": 0.0025426464,
          "pixel_fraction": 0.066761464,
          "red": 9,
          "green": 13,
          "blue": 2
        }],
        "#203911": [{
          "hex": "#203911",
          "score": 0.021619858,
          "pixel_fraction": 0.08972627,
          "red": 32,
          "green": 57,
          "blue": 17
        }],
        "#306112": [{
          "hex": "#306112",
          "score": 0.052881327,
          "pixel_fraction": 0.09228582,
          "red": 48,
          "green": 97,
          "blue": 18
        }],
        "#4c871a": [{
          "hex": "#4c871a",
          "score": 0.08929054,
          "pixel_fraction": 0.08275862,
          "red": 76,
          "green": 135,
          "blue": 26
        }],
        "#538333": [{
          "hex": "#538333",
          "score": 0.045829047,
          "pixel_fraction": 0.056096695,
          "red": 83,
          "green": 131,
          "blue": 51
        }],
        "#6ab61c": [{
          "hex": "#6ab61c",
          "score": 0.052289702,
          "pixel_fraction": 0.02047636,
          "red": 106,
          "green": 182,
          "blue": 28
        }],
        "#6fab37": [{
          "hex": "#6fab37",
          "score": 0.08954284,
          "pixel_fraction": 0.05872734,
          "red": 111,
          "green": 171,
          "blue": 55
        }],
        "#784835": [{
          "hex": "#784835",
          "score": 0.07421559,
          "pixel_fraction": 0.019836474,
          "red": 120,
          "green": 72,
          "blue": 53
        }],
        "#8bd334": [{
          "hex": "#8bd334",
          "score": 0.13494858,
          "pixel_fraction": 0.031567723,
          "red": 139,
          "green": 211,
          "blue": 52
        }],
        "#96d058": [{
          "hex": "#96d058",
          "score": 0.052115206,
          "pixel_fraction": 0.024600072,
          "red": 150,
          "green": 208,
          "blue": 88
        }]
      },
      "nsfw": [{
        "label": "sfw",
        "score": 0.9918149
      }, {
        "label": "nsfw",
        "score": 0.008185141
      }, {
        "label": "adult",
        "likelihood": "VERY_UNLIKELY"
      }, {
        "label": "violence",
        "likelihood": "VERY_UNLIKELY"
      }, {
        "label": "spoof",
        "likelihood": "VERY_UNLIKELY"
      }, {
        "label": "medical",
        "likelihood": "VERY_UNLIKELY"
      }, {
        "label": "safe",
        "score": 0.9983775329589839
      }]
    }]
  }
}
```

This endpoint retrieves an async response from a video or batch request.

### HTTP Request

`GET https://api.visionati.com/api/response/<request_id>`

### URL Parameters

This endpoint takes no parameters.
