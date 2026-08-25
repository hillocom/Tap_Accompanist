# Tap Accompanist 🎹

**Tap Accompaniment Player for Standard MIDI Files (SMF)**  
ピアノが弾けなくても大丈夫！生徒やボーカルの歌声・呼吸に合わせて、タップひとつで自由自在に伴奏できるリアルタイムSMFプレイヤーです。  
*No piano skills required! Accompany singers in real time by simply tapping along with their natural pace, tempo, and phrasing.*

[日本語](#日本語) | [English](#english)

---

<a name="日本語"></a>
## 🇯🇵 日本語

### 概要
`Tap Accompanist` は、スタンダードMIDIファイル（SMF Format 0 / 1）を読み込み、キーボードやMIDI機器をポンと叩くだけで、1ステップずつリアルタイムに伴奏を進行させられるWebアプリケーションです。

あらかじめ決まったテンポに人間が合わせる従来の再生ソフトとは異なり、**「歌い手のテンポ感や呼吸に寄り添って伴奏をコントロールする」** 演奏を実現します。ピアノ演奏の技術がなくても、音楽レッスンやボーカル練習で自然で柔軟な伴奏を簡単に提供できます。

サーバー通信を行わない完全クライアントサイド（ブラウザ内）処理のため、通信遅延が一切なく、オフライン環境でも超低レイテンシーな演奏が可能です。

### 主な特徴
- **SMF（Format 0 / 1）完全対応**: 16チャンネルのマルチトラック演奏に対応。
- **10Chドラム保護**: 移調（Transpose）設定時もドラムトラック（10Ch）は自動判別され、打楽器ノートのピッチズレを防止。
- **プログラムチェンジ / CC対応**: 音色指定（PC）の送出ON/OFF切替、バンクセレクト、サステインペダル（CC64）等の信号に対応。
- **柔軟な打鍵インプット**: キーボード（最大4キー割り当て）、ペダルキー、接続された外部MIDIキーボード/パッド入力をサポート。
- **動的BPM追従**: タップの打鍵間隔に合わせてBPMをリアルタイム自動更新。
- **Web MIDI API連携**: loopMIDIやIACバスを経由し、各種DAW（Logic, REAPER, Cubase等）や外部音源（VSTi / GM音源）へダイレクト出力。
- **バイリンガルUI**: 日本語 / 英語のワンクリック表示切替。
- **折りたたみ設定UI**: 演奏中は設定パネルをコンパクトに収納可能。

### 使い方
1. **MIDIファイルの読み込み**: 「ファイルを選択」から任意の `.mid` / `.midi` ファイルを読み込みます。
2. **出力音源の選択**: 内部Web音源（Tone.js）または接続されている外部MIDIポート（loopMIDI / IACバス / ハードウェア音源等）を選択します。
3. **キー・MIDI設定 (オプション)**: ⚙️アコーディオンを開き、打鍵に使用するキー（最大4つ）やペダルキー、入力MIDI機器を設定します。
4. **刻み・移調の設定**: 1拍（4分）、1/2拍（8分）、1/3拍（8分3連）、1/4拍（16分）から演奏刻みを選択します。
5. **演奏（タップ）**: 画面中央のボタン、割り当てたキー、または接続したMIDI機器を叩いて伴奏を進行させます。

---

<a name="english"></a>
## 🇺🇸 English

### Overview
`Tap Accompanist` is a browser-based Web application that lets you advance Standard MIDI Files (SMF) step-by-step in real time using simple key taps or MIDI inputs. 

Unlike traditional playback tools that force singers to follow a rigid metronome, it allows you to **adapt the accompaniment to the singer's natural tempo, phrasing, and breath** in real time. It serves as an ideal accompaniment solution for vocal lessons, practice sessions, and live performances—even without piano playing skills.

Running 100% locally in your browser, it delivers ultra-low latency without requiring server processing or an active internet connection.

### Features
- **Full SMF (Format 0 / 1) Support**: Multi-track playback handling up to 16 MIDI channels.
- **Automatic Drum Track Protection**: Channel 10 (Drums) is automatically detected and excluded from transpose adjustments to prevent pitch shifting of percussion sounds.
- **Program Change & Control Change Handling**: Toggle Program Change (instrument selection) output ON/OFF; supports Bank Select and Sustain Pedal (CC64) events.
- **Versatile Input Mapping**: Assign up to 4 keyboard keys, a pedal key, or physical MIDI controller buttons.
- **Dynamic BPM Follow**: Automatically calculates and updates BPM based on your tapping speed.
- **Web MIDI API Integration**: Seamlessly route MIDI out to DAWs (Logic, REAPER, Cubase, etc.) or external synths via loopMIDI / IAC Bus.
- **Bilingual Interface**: Switch between English and Japanese instantly.
- **Collapsible Settings UI**: Clean, clutter-free interface with accordion-style settings panel.

### How to Use
1. **Load MIDI File**: Click "Choose File" to upload your `.mid` or `.midi` file.
2. **Select MIDI Output**: Choose between the internal synth (Tone.js) or any connected MIDI Output (loopMIDI, IAC Bus, or hardware synths).
3. **Key / MIDI Setup (Optional)**: Expand the ⚙️ Settings accordion to assign keys or select your input MIDI device.
4. **Set Step & Transpose**: Choose your playback resolution (Quarter, 8th, 8th Triplet, or 16th notes).
5. **Tap to Play**: Press the tap button, assigned keyboard keys, or your MIDI controller to drive the accompaniment.

---

## 技術スタック (Tech Stack)
- **HTML5 / CSS3 / JavaScript (ES6+)**
- **[Tone.js](https://tonejs.github.io/)**: Internal audio synthesis and timing
- **[@tonejs/midi](https://github.com/Tonejs/Midi)**: SMF parsing
- **Web MIDI API**: Direct MIDI I/O handling in browser

## ライセンス (License)
MIT License
