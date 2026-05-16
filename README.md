# AIOStreams template by 06Maxx

A custom template for [AIOStreams](https://github.com/Viren070/AIOStreams) that gives your Stremio stream list a clean, clear, and easy to read layout.

---

### Preview
<img width="700" height="220" alt="firefox 2026-16-05 125540" src="https://github.com/user-attachments/assets/ab5439ed-70e3-466a-a7c9-d10ac52ae09b" />

---

## Usage

Paste each template into the corresponding field in your AIOStreams ``formatting`` configuration.

### 1. Name template

Displays the debrid service, cache status (⚡ cached / ☁️ uncached), addon name, and resolution.

```
{service.shortName::exists["[{service.shortName}"||""]}{service.cached::istrue["⚡]"||""]}{service.cached::isfalse["☁️]"||""]} {addon.name} {stream.resolution::replace('2160p','4K⠀⠀⠀')::replace('1440p','2K⠀⠀⠀')::replace('1080p','1080p⠀⠀⠀')::replace('720p','720p⠀⠀⠀')}
```

### 2. Description Template

Shows stream details including title, quality, file size, indexer, audio, and languages.

```
🎬 {stream.seasonEpisode::exists["{stream.seasonEpisode::join(' ')} · "||""]}{stream.filename::~complete["Complete · "||""]}{stream.filename::~extended["Extended · "||""]}{stream.title}{stream.year::exists[" ({stream.year})"||""]}
🎞️ {stream.quality::exists["{stream.quality::replace('BluRay REMUX','REMUX')}"||"xxx"]}{stream.visualTags::exists[" · {stream.visualTags}"||" · {stream.encode}"]}
📦 {stream.size::bytes}{stream.bitrate::exists[" · {stream.bitrate::sbitrate}"||""]}
🔊 {stream.audioChannels::exists["{stream.audioChannels::join(' · ')} "||""]}{stream.audioTags::exists["{stream.audioTags::join(' · ')}"||"Unknown"]} 
🌍 {stream.languages::exists["{stream.smallLanguageCodes::join(' · ')::replace('ᴅᴜᴀʟ ᴀᴜᴅɪᴏ','ᴅᴜᴏ')::replace('ᴅᴜʙʙᴇᴅ','ᴅᴜʙ')}"||"ᴏʀɪɢɪɴᴀʟ"]}
{stream.editions}
```

### Each template can also be altered to your specific requirements!

---

## Description field reference

| Icon | Field | Description |
|------|-------|-------------|
| 🎬 | Title | Season/episode, special edition flags, title, and year |
| 🎞️ | Quality | REMUX label or quality string, plus visual tags/encode |
| 📦 | Size | File size in human-readable bytes + bitrate in Mbps|
| 🔊 | Audio | Channel layout and audio format tags |
| 🌍 | Languages | Language codes; falls back to `ᴏʀɪɢɪɴᴀʟ` |
