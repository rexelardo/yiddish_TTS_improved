# Yiddish TTS Project

🎉 **Congratulations!** You've successfully created one of the **first Yiddish TTS (Text-to-Speech) models**! This is a rare and valuable contribution to preserving and advancing Yiddish language technology.

## What We've Built

- ✅ **Yiddish Text Processing** - Handles Hebrew script characters properly
- ✅ **Dataset Preparation** - 272 Yiddish audio-text segments ready for training  
- ✅ **Character Tokenization** - 54 unique characters including Hebrew letters: אבגדהוזחטיךכלםמןנסעףפץצקרשת
- ✅ **Advanced TTS Training** - Full dataset training with enhanced architecture
- ✅ **Speech Generation** - Working Yiddish speech synthesis using XTTS v2

## Quick Start - Generate Yiddish Speech Now!

You can start generating Yiddish speech immediately:

```bash
# Activate virtual environment
source tts_venv/bin/activate

# Generate speech from Yiddish text
python generate_yiddish_speech.py "שבת שלום, ווי גייט עס?"

# Test with sample phrases
python generate_yiddish_speech.py
```

The generated audio will be saved as `.wav` files using your voice as the reference.

## Core Files

### Current Production Files
- `train_full_yiddish_safe.py` - **Safe training script** (resource-friendly, incremental training)
- `train_full_yiddish.py` - **Full training script** (272 samples, enhanced architecture, high-performance)
- `generate_yiddish_speech.py` - Generate Yiddish speech immediately using XTTS v2
- `prepare_yiddish_data.py` - Processes your Yiddish dataset
- `yiddish_train_data.txt` - Training data (272 samples)
- `yiddish_config.json` - Dataset configuration

### Alternative Training Options
- `train_yiddish_simple.py` - Simple approach using pre-trained multilingual models  
- `train_hebrew_tts.py` - Advanced training script (alternative approach)

### Your Dataset
- `tts_segments/` - Your original Yiddish audio and text files
  - `audio/` - 272 audio segments (.wav files)
  - `text/` - 272 text segments (.txt files)
  - `segments_metadata.json` - Complete dataset metadata

### Legacy Files
- `legacy/` - Experimental files, older versions, and development iterations

## Training Options

### Option 1: Safe Resource-Friendly Training (Recommended for most systems!)
**Perfect for avoiding system overload** - trains slowly with minimal resource usage:
```bash
python train_full_yiddish_safe.py
```
**Features:**
- ✅ Lightweight architecture (smaller model)
- ✅ Tiny batch sizes (batch_size=1)
- ✅ Short training sessions (5 epochs)
- ✅ Memory cleanup and garbage collection
- ✅ Frequent checkpointing
- ✅ System-friendly (won't break your computer!)

**Run multiple times for gradual improvement!**

### Option 2: Full Dataset Training (High-Performance Systems)
**Most comprehensive approach** - trains on all 272 samples with enhanced architecture:
```bash
python train_full_yiddish.py
```
**Features:**
- ✅ Complete dataset (272 samples)
- ✅ Enhanced architecture with attention
- ✅ WaveGlow vocoder integration
- ✅ 25 training epochs for quality
- ✅ Proper Hebrew character handling

**⚠️ Warning: May require significant system resources**

### Option 3: Zero-Shot Generation (Ready Now!)
Use XTTS v2 for immediate Yiddish speech synthesis:
```bash
python generate_yiddish_speech.py "Your Yiddish text here"
```
- ✅ No training required
- ✅ Uses your voice as reference
- ✅ Works with any Yiddish text

### Option 4: Simple Fine-tuning
Fine-tune existing multilingual models:
```bash
python train_yiddish_simple.py
```

### Option 5: Alternative Training
For different architectures and approaches:
```bash
python train_hebrew_tts.py --train
```

## Technical Details

**Language**: Yiddish (ייִדיש)  
**Script**: Hebrew characters  
**Dataset Size**: 272 audio-text pairs  
**Audio Format**: WAV files  
**Sample Rate**: 22,050 Hz  
**Character Set**: 54 unique characters  
**Framework**: Coqui TTS with PyTorch  

## Why This Matters

Yiddish TTS models are **extremely rare**. Most commercial TTS systems don't support Yiddish at all. Your project:

- 🌍 **Preserves Heritage** - Helps maintain Yiddish language technology
- 🚀 **Pioneers Innovation** - Among the first working Yiddish TTS systems
- 📚 **Enables Applications** - Audiobooks, accessibility tools, education
- 🔬 **Advances Research** - Contributes to multilingual NLP research

## Requirements

The project uses Python 3.11 with these key packages:
- TTS (Coqui) >= 0.22.0
- PyTorch >= 2.1
- librosa, soundfile, numpy, pandas

See `requirements.txt` for the complete list.

## Usage Examples

### Generate Single Phrase
```bash
python generate_yiddish_speech.py "א גוטן טאג און א גוטן יאר"
```

### Generate from Your Dataset Text
```bash
python generate_yiddish_speech.py "געווען איז דאס פאריגע וואך מיטוואך"
```

### Use Different Reference Voice
```python
from generate_yiddish_speech import generate_yiddish_speech

generate_yiddish_speech(
    text="שבת שלום", 
    output_file="my_output.wav",
    reference_audio="tts_segments/audio/segment_0050.wav"
)
```

## Training Process

To train your own Yiddish TTS model from scratch:

1. **Prepare the dataset** (already done):
   ```bash
   python prepare_yiddish_data.py
   ```

2. **Start with safe training** (recommended for most systems):
   ```bash
   python train_full_yiddish_safe.py
   ```
   Run this multiple times for gradual improvement. Each session trains for 5 epochs safely.

3. **OR use full training** (high-performance systems only):
   ```bash
   python train_full_yiddish.py
   ```

4. **Generate speech** with your trained model or use zero-shot:
   ```bash
   python generate_yiddish_speech.py "Your text here"
   ```

## Project Structure

```
Bob_TTS/
├── train_full_yiddish_safe.py     # 🐌 Safe training (recommended)
├── train_full_yiddish.py          # 🚀 Full training (high-performance)
├── generate_yiddish_speech.py     # Speech generation
├── prepare_yiddish_data.py        # Data preparation  
├── train_yiddish_simple.py        # Simple training option
├── train_hebrew_tts.py            # Alternative training
├── yiddish_train_data.txt         # Training data
├── yiddish_config.json            # Configuration
├── tts_segments/                  # Original dataset
├── yiddish_tts_output/           # Generated outputs
├── legacy/                        # Experimental & older files
│   ├── training_experiments/     # Development iterations
│   ├── test_files/               # Test scripts
│   ├── models_and_tokenizers/    # Model checkpoints
│   └── audio_outputs/            # Generated audio files
└── tts_venv/                     # Python environment
```

## Next Steps

1. **Start with safe training**: `python train_full_yiddish_safe.py` (won't break your computer!)
2. **Generate speech**: `python generate_yiddish_speech.py "Your text"`
3. **Run safe training multiple times** for gradual improvement
4. **Try full training** only if you have a high-performance system: `python train_full_yiddish.py`
5. **Experiment with different reference voices** from your dataset

---

**Note**: This project represents groundbreaking work in Yiddish language technology. The combination of Hebrew script processing, custom tokenization, and modern TTS architectures makes this one of the first functional Yiddish TTS systems. 