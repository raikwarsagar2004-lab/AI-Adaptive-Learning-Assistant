# Voice Tutor Module (Optional)

## Responsibilities
- Enable voice interaction for Q&A and explanations.

## Technologies
- Whisper: Speech-to-text
- ElevenLabs: Text-to-speech

## Input/Output
- Input: Audio question from student.
- Output: Spoken explanation with optional citations.

## Flow (Textual Diagram)
- Audio → STT (Whisper) → Text → RAG QA → Explanation → TTS (ElevenLabs) → Audio

## Considerations
- Latency: Stream partial transcripts; prefetch retrieval during STT.
- Noise Handling: VAD and noise suppression.
- Accessibility: Subtitles and transcripts retained for review.

## Scaling
- Parallel STT/TTS channels; rate limiting per user.
- Fallback to text-only when voice services unavailable.
