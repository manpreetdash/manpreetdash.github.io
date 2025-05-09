---
title: More notes on AI search
subtitle: What happens next
layout: blog
---

Testing bsky comments

<link rel="stylesheet" href="https://unpkg.com/bluesky-comments@<VERSION>/dist/bluesky-comments.css">

<script type="importmap">
{
  "imports": {
    "react": "https://esm.sh/react@18",
    "react-dom/client": "https://esm.sh/react-dom@18/client"
  }
}
</script>

<script type="module">
  import {BlueskyComments} from 'https://unpkg.com/bluesky-comments@0.8.0/dist/bluesky-comments.es.js';

  document.addEventListener('DOMContentLoaded', function() {
    const uri = 'https://bsky.app/profile/tomcritchlow.com/post/3lojrnoum5k2r';
    const author = 'coryzue.com';
    BlueskyComments.init('bluesky-comments', {
      uri,
      author,
      commentFilters: [BlueskyComments.Filters.NoPins],
    });
  });
</script>

<div id="bluesky-comments"></div>

