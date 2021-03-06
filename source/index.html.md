---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://api.visionati.com'>Sign Up for an API Key</a>
  - <a href='https://github.com/visionati/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Visionati API! You can use our API to analyze images and videos. You can fetch a variety of data including tags, faces, brands, colors, and text. You can even scan YouTube and Vimeo videos!

The API runs on credits. Each image or frame of video requires 1 credit. You can easily buy additional credits at our [API server](https://api.visionati.com).

# Authentication

> To authorize, use this code:

```shell
# You need to pass the correct header with each request.
curl "<API_ENDPOINT>"
  -H "Authorization: Token <YOUR_API_KEY>"
```

> Make sure to replace `<YOUR_API_KEY>` with your API key.

Visionati uses API keys to allow access to the API. You can register an account at our [API server](https://api.visionati.com).

Visionati expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Token <YOUR_API_KEY>`

<aside class="notice">
You must replace <code>&lt;YOUR_API_KEY&gt;</code> with your API key.
</aside>

# Visionati

## Analyze an Image/Video

```shell
# Sample call to analyze an image.
curl "https://api.visionati.com/api/fetch?url=https%3A%2F%2Fmedia.treehugger.com%2Fassets%2Fimages%2F2016%2F07%2Fgreen-forest-trees.jpg.860x0_q70_crop-scale.jpg"
  -H "Authorization: Token <YOUR_API_KEY>"
```

> The command above returns the following JSON. The second response below is returned if you request multiple images/videos.

```json
{
  "request_id": "c36131f5-a040-4992-9741-91f2d3852ac3",
  "user_id": 1,
  "urls": ["https://media.treehugger.com/assets/images/2016/07/green-forest-trees.jpg.860x0_q70_crop-scale.jpg"],
  "features": [],
  "backends": [],
  "tag_score": 0.8,
  "capture_interval": 0,
  "credits": 858,
  "credits_paid": 1,
  "all": {
    "assets": [{
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

> Response if you sent a batch request.

```json
{
  "request_id": "267f99ce-c797-4855-807f-21b204edb7ed",
  "user_id": 1,
  "urls": ["https://i.imgur.com/XUXe335.jpg", "https://media.treehugger.com/assets/images/2016/07/green-forest-trees.jpg.860x0_q70_crop-scale.jpg"],
  "features": [],
  "backends": [],
  "tag_score": 0.8,
  "capture_interval": 0,
  "success": true,
  "response_uri": "https://api.visionati.com/api/response/267f99ce-c797-4855-807f-21b204edb7ed"
}
```

This is the main endpoint of the API, and is used to analyze an image or video. If you pass it multiple images/videos to scan then it will provide a different response with a `response_uri` to poll for results.

### HTTP Request

`GET https://api.visionati.com/api/fetch`

### Query Parameters

Parameter | Required | Default | Description
--------- | -------- | ------- | -----------
url | true | none | URL to the image/video you wish to scan. Videos return an async response.
url[] | true | none | URLs to the images/videos you wish to analyze. This param should be passed multiple times. Returns an async response.
feature | false | all | Select features you want to enable. By default all features are enabled. Valid values are: brands, colors, faces, nsfw, tags, texts.
feature[] | false | all | Allows you to pass multiple features at the same time. That way you can just scan tags and faces if you want.
tag_score | false | 0.8 | Minimum tag score for the results. Valid values are floats between 0 and 1.
capture_interval | false | 1 | By default videos process every frame. This allows you to set the capture interval. Valid values are integers greater than 0.

<aside class="success">
Remember - anytime you see a param that ends in [], you can use it multiple times!
</aside>

## Async Response

```shell
curl "https://api.visionati.com/api/response/267f99ce-c797-4855-807f-21b204edb7ed"
  -H "Authorization: Token <YOUR_API_KEY>"
```

> The command above returns the following JSON as it is processing. The second response below is returned if processing is complete.

```json
{
  "request_id": "267f99ce-c797-4855-807f-21b204edb7ed",
  "user_id": 1,
  "urls": ["https://i.imgur.com/XUXe335.jpg", "https://media.treehugger.com/assets/images/2016/07/green-forest-trees.jpg.860x0_q70_crop-scale.jpg"],
  "features": [],
  "backends": [],
  "tag_score": 0.8,
  "capture_interval": 0,
  "status": "processing"
}
```

> Response when processing is complete.

```json
{
  "request_id": "267f99ce-c797-4855-807f-21b204edb7ed",
  "user_id": 1,
  "urls": ["https://i.imgur.com/XUXe335.jpg", "https://media.treehugger.com/assets/images/2016/07/green-forest-trees.jpg.860x0_q70_crop-scale.jpg"],
  "features": [],
  "backends": [],
  "tag_score": 0.8,
  "capture_interval": 0,
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
