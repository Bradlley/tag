Code Snippet:
        AudioFile audioFile = null;
        MP3File mp3File;
        try {
            audioFile = AudioFileIO.read(new File(item.getPath()));
            org.jaudiotagger.tag.Tag tag = audioFile.getTag();
            if(tag != null) {
                String title = tag.getFirst(FieldKey.TITLE);
                String artist = tag.getFirst(FieldKey.ARTIST);
                String album = tag.getFirst(FieldKey.ALBUM);
                if(tag.getFirstArtwork() != null) {
                    byte[] artworkBytes = tag.getFirstArtwork().getBinaryData();
                }

            }

        } catch (CannotReadException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } catch (TagException e) {
            e.printStackTrace();
        } catch (ReadOnlyFileException e) {
            e.printStackTrace();
        } catch (InvalidAudioFrameException e) {
            e.printStackTrace();
        }


References: https://github.com/hexise/jaudiotagger-android
            http://www.jthink.net/jaudiotagger/examples_read.jsp
