# React

## ディレクトリ構成
Reactはディレクトリ構成のルールがない。
プロジェクトごとに最適な穂不応は違うはずだから、好きにしてねというスタイルらしい。

### 方法1. Grouping by features or routes
```
common/
├─ Avatar.js
├─ Avatar.css
├─ APIUtils.js
└─ APIUtils.test.js
feed/
├─ index.js
├─ Feed.js
├─ Feed.css
├─ FeedStory.js
├─ FeedStory.test.js
└─ FeedAPI.js
profile/
├─ index.js
├─ Profile.js
├─ ProfileHeader.js
├─ ProfileHeader.css
└─ ProfileAPI.js
```

### 方法2.Grouping by file type
```
api/
├─ APIUtils.js
├─ APIUtils.test.js
├─ ProfileAPI.js
└─ UserAPI.js
components/
├─ Feed.js
├─ Feed.css
├─ FeedStory.js
├─ Profile.js
├─ ProfileHeader.js
└─ ProfileHeader.css
containers/
├─ Feed.js
└─ Profile.js
```
