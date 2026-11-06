## Three things a caller can do to a playlist that makes no sense

1. playlist.trimToSize() : This is a memory-management method used to shrink an array's capacity. A caller listening to music has no business managing the internal memory footprint of the playlist.
-----------------------------------------
2. playlist.retainAll(otherCollection): This performs a mathematical set intersection, keeping only elements present in another collection. This is a bulk data operation, not a valid domain action for managing songs.
-----------------------------------------
3. playlist.subList(0, 5).clear(): A caller can grab a structural sub-view of the playlist and instantly wipe out a chunk of songs, completely bypassing any playback or state-tracking logic the Playlist might be trying to enforce.