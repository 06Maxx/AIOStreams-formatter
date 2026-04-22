# AIOStreams template by 06Maxx

A template for [AIOStreams](https://github.com/Viren070/AIOStreams) that gives your Stremio stream list a clean, clear, and easy to read layout.

---

### Preview

<img width="524" height="170" alt="AIOStreams stream selection preview" src="https://github.com/user-attachments/assets/0345c24e-cbcd-46f0-abe0-cbb2ec31bd2a" />

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
🎬 {stream.seasonEpisode::exists["{stream.seasonEpisode::join(' · ')} · "||""]}{stream.filename::~complete["(Complete) "||""]}{stream.filename::~extended["(Extended) "||""]}{stream.title}{stream.year::exists[" ({stream.year})"||""]}
🎞️ {stream.filename::~remux["BR REMUX"||"{stream.quality}"]} 🏷️ {stream.visualTags::exists["{stream.visualTags}"||"{stream.encode}"]}
📦 {stream.size::bytes} 📡 {stream.indexer::exists["{stream.indexer}"||"NA"]}
🔊 {stream.audioChannels::exists["{stream.audioChannels::join(' · ')} "||""]}{stream.audioTags::exists["{stream.audioTags::join(' · ')}"||"Unknown"]}
🌍 {stream.languages::exists["{stream.smallLanguageCodes::join(' · ')::replace('ᴅᴜᴀʟ ᴀᴜᴅɪᴏ','ᴅᴜᴏ')::replace('ᴅᴜʙʙᴇᴅ','ᴅᴜʙ')}"||"ᴏʀɪɢɪɴᴀʟ"]}
```

### Each template can also be altered to your specific requirements!

---

## Description field reference

| Icon | Field | Description |
|------|-------|-------------|
| 🎬 | Title | Season/episode, special edition flags, title, and year |
| 🎞️ | Quality | BR REMUX label or quality string, plus visual tags/encode |
| 📦 | Size | File size in human-readable bytes |
| 📡 | Indexer | Source indexer, falls back to `NA` |
| 🔊 | Audio | Channel layout and audio format tags |
| 🌍 | Languages | Language codes; falls back to `ᴏʀɪɢɪɴᴀʟ` |
