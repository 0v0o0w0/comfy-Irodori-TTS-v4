# comfy_IrodoriTTS

Fork元: https://github.com/jupo-ai/comfy-Irodori-TTS
ComfyUIで[Irodori-TTS](https://github.com/Aratako/Irodori-TTS)を使うためのカスタムノードです。

本カスタムノードは、Irodori-TTSと、そのフォーク版である[Emoji-TTS](https://github.com/iron-mukakin/Emoji-TTS)を元に、
[jupo-ai](https://github.com/jupo-ai)氏が作られたノードをv4用に改修したものです。

また、改修にはClaudeのSonnet5を大幅に利用しております。間違い等がございましたら指摘ください。

# 変更点
- 以下のファイルを本家[Irodori-TTS](https://github.com/Aratako/Irodori-TTS)から拝借し、`\comfy-Irodori-TTS\py\modules\irodori_tts\`に配置
    - `config.py`
    - `model.py`
    - `speaker_inversion.py`
- `comfy-Irodori-TTS\py\modules\irodori_tts\__init__.py`から、本家で削除された`SamplingConfig`クラスを削除
- `comfy-Irodori-TTS\py\modules\irodori_tts\inference_runtime.py`を修正
    - `def _split_flat_checkpoint_config(path: Path, flat_config: dict) -> tuple[dict, dict | None]:`を変更
    - `elif self.model_cfg.use_duration_predictor`を変更
    - `self.model_cfg.use_speaker_condition`から`self.model_cfg.use_speaker_condition_resolved`に変更

> さらに詳細はv4_compatibility_patch_summary.mdをご確認ください

## ライセンス

このカスタムノードのライセンスはリポジトリ内の[LICENSE](./LICENSE)を確認してください。

Irodori-TTS本体、Emoji-TTS、および各モデルのライセンスは、それぞれの配布元を確認してください。
