# Installing and configuring AIKit

## Supported models

4D AIKit supports OpenAI models and models from any OpenAI-compatible API provider. The component is designed to work seamlessly with various AI providers through a unified interface.

Here’s the link to OpenAI different models: **[https://platform.openai.com/docs/models](https://platform.openai.com/docs/models)**

## Basic API Configuration

The AIKit component is initialized through the cs.AIKit.OpenAI class, requiring an API key and optional configuration parameters. The configuration supports custom endpoints for OpenAI-compatible services, parameter settings, and default model preferences.

```4d
// Basic configuration
var $aiClient : cs.AIKit.OpenAI
$aiClient:=cs.AIKit.OpenAI.new("your-api-key-here")
// Configuration with custom settings
var $config : Object
$config:=New object
$config.model:="gpt-4o-mini"
$config.temperature:=0.7
$config.maxTokens:=1000
$aiClient:=cs.AIKit.OpenAI.new("your-api-key-here"; $config)
```

## 
Configuration parameters

model: used to choose the AI model based on the purpose (text generation, image generation, and etc.)

temperature**:** Used to control the randomness and creativity of responses &#8211; lower values produce consistent outputs, higher values generate more varied responses

maxTokens**:** Used to limit the maximum length of the generated response and control API costs

timeout**:** Used to set the maximum wait time for API responses before terminating the request

And much more specified in the documentation.

*Before getting an API Key from cloud AI provider, a local test might be done using Local Provider*
*like Ollama, please check this tech tip for more details : *[*Testing 4D AIKit Without an OpenAI API*
*Key*](https://kb.4d.com/assetid=79903)