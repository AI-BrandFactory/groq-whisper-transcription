# Groq Whisper Transcription in 50 Lines

A 50-line Node.js service that transcribes a folder of audio files using Groq's Whisper-large-v3-turbo. Around 250x realtime, $0.04 per audio hour, drop-in replacement for OpenAI Whisper. Full code, format handling for m4a/mp3/wav/mp4, chunking strategy for files over 25MB, the three errors you will hit, and three real pipelines.

---

> **Part of the AI BrandFactory open toolkit.**
> Free to use and adapt with attribution.
> More tools, templates, and AI systems at [aibrandfactory.com](https://www.aibrandfactory.com)

---

## What's Inside

- Why Groq Whisper beats OpenAI Whisper in 2026. Groq runs Whisper-large-v3-turbo at 250x realtime vs OpenAI's 5 to 10x. Pricing $0.04/audio hour vs OpenAI's $0.36. Quality parity on same model weights. Where OpenAI still wins: long-context streaming, built-in diarization.
- The 50-line service in one file. Node.js, fs plus axios plus form-data, no exotic dependencies. The full code block, then a section-by-section walkthrough so you understand every line. Reads a folder, loops files, posts to Groq, writes the transcript to disk. That is the whole shape.
- End-to-end setup in 5 minutes. Get a Groq API key from console.groq.com. Run npm install. Drop a placeholder .env. Point the script at your audio folder. First transcript hits disk before your coffee finishes brewing. The exact commands and the exact .env template.
- Format handling for the four formats you encounter. m4a, mp3, wav go straight to the API. mp4 needs a one-line ffmpeg pre-step. Groq's 25MB ceiling and the chunking strategy. Ffmpeg commands to split a 90-min interview into 15-min chunks and stitch transcripts with offset timestamps.
- The three errors you will hit and how to fix them. The 429 rate limit (5-line backoff wrapper). The file-too-large error (chunking pattern from Part 4). Garbage transcription from low-quality recordings (the ffmpeg preprocess command that fixes most bad-audio cases).
- Three real pipelines you can ship this week. Podcast episode: 60-minute episode in 90 seconds with timestamps, ready for show notes. Meeting recording to action items: transcribe + downstream LLM call. Course video to searchable transcript library: chapter-tagged + indexed for student search.

## Files

- `playbook.md` — full playbook source in Markdown
- `playbook.pdf` — rendered PDF for download / sharing
- `copy.json` — title, hook, benefits, schema for re-publishing
- `image-prompts.json` — Gemini prompts for the brand 4 images (cover, hero, og, notion-cover)
- `embedded-prompts.json` — Gemini prompts for the embedded tactical visuals


## Read or Download

- Live page: [files.aibrandfactory.com/playbooks/groq-whisper-transcription](https://files.aibrandfactory.com/playbooks/groq-whisper-transcription)
- Notion duplicatable template: [https://massiveimpact.notion.site/Groq-Whisper-Transcription-in-50-Lines-34ffb27e663481d89291f426f6970d49](https://massiveimpact.notion.site/Groq-Whisper-Transcription-in-50-Lines-34ffb27e663481d89291f426f6970d49)

## Use

Fork this repo, edit `playbook.md` for your own audience or customize the prompts in `image-prompts.json` to re-skin for your brand. Attribution required per LICENSE.

## License

Free to use with attribution. See [LICENSE](LICENSE) for details.

Built by [AI BrandFactory](https://www.aibrandfactory.com), tools and systems for AI-powered content businesses.
