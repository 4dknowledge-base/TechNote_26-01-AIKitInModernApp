# Overview of AIKit in 4D

## Component overview and capabilities

4D AIKit is a built-in comprehensive component that provides three primary functional areas through the `cs.AIKit namespace`:

### 
Text Generation and Processing

The chat completions API enables human-like text generation for content creation,summarization, translation, and data transformation. This functionality supportsgenerating reports, emails, product sescriptions, or any text-based output required in business applications. The component maintains conversation context through message collections, enabling multi-turn dialogues with maintained state.

### 
Vision and Image Analysis

**Vision capabilities** extract information from **images**, **documents**, and **visual content**. This enables optical character recognition, object detection, and visual question answering without requiring specialized image processing infrastructure. 
The **vision helper class** simplifies **image analysis** by combining chat completions with image input.

### 
Image Generation

The images API generates visual content from text descriptions, enabling applications to create illustrations, placeholders, or design concepts programmatically. This capability supports creative workflows and automated asset generation.

The 4D AIKit component is structured around several core classes that provide organized access to above AI capabilities:

Class&nbsp;Purpose&nbsp;Example CodeOpenAI&nbsp;Main client class for API authentication and configuration. Entry point for all AIKit functionality.$aiClient := cs.AIKit.OpenAI.new(&#8220;api-key&#8221;) 

// With config 
$config := New object(&#8220;model&#8221;; &#8220;gpt-4o-mini&#8221;) 
$aiClient := cs.AIKit.OpenAI.new(&#8220;api-key&#8221;; $config)OpenAIChatCompletionsAPIHandles text generation and chat-based AI interactions. Processes conversation messages and returns AI responses.$messages := New collection 
$messages.push(New object(&#8220;role&#8221;; &#8220;user&#8221;; &#8220;content&#8221;; &#8220;Explain AI&#8221;)) $result := 
$aiClient.chat.completions.create($messages; $options)OpenAIVision/ OpenAIVisionHelperSpecialized helper for vision tasks, image analysis, OCR, visual question answering, and document extraction.$vision := $aiClient.chat.vision.fromFile($file) 
$params := New object(&#8220;model&#8221;; &#8220;gpt-4o&#8221;) 
$result := $vision.prompt(&#8220;Extract text&#8221;; $params)OpenAIImagesAPI&nbsp;Handles AI-powered image generation from text descriptions for creating visual assets.$prompt := &#8220;Business dashboard&#8221; 
$options := New object(&#8220;model&#8221;; &#8220;dall-e-3&#8221;; &#8220;size&#8221;; &#8220;1024&#215;1024&#8221;) $result := 
$aiClient.images.generate($prompt; $options)