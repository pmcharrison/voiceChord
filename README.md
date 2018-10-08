
voiceR v0.0.0.9000
==================

Chord sequences can be voiced in different ways, some better than others. This package, `voiceR`, tries to find optimal voicings for chord sequences.

Status: **pre-alpha**

Example usage
-------------

`voice_pc_set_seq` finds the optimal voicing for a series of pitch class sets.

``` r
library(voiceR)
pc_sets <- list(c(0, 4, 7), c(0, 5, 9), c(2, 7, 11), c(0, 4, 7))
voice_pc_set_seq(pc_sets)
#> [[1]]
#> [1] 52 60 67
#> 
#> [[2]]
#> [1] 53 60 69
#> 
#> [[3]]
#> [1] 50 59 67
#> 
#> [[4]]
#> [1] 52 60 67
#> 
#> attr(,"cost")
#> [1] 19.23183
```

`revoice_midi_chord_seq` takes a sequence of MIDI chords as input and returns an optimally revoiced sequence, ensuring that:

-   the pitch class of the bass note is preserved;
-   any duplicated pitch classes are preserved.

``` r
midi <- list(c(60, 64, 67), c(60, 65, 69), c(62, 67, 611), c(60, 64, 67))
revoice_midi_chord_seq(midi)
#> [[1]]
#> [1] 48 64 67
#> 
#> [[2]]
#> [1] 48 65 69
#> 
#> [[3]]
#> [1] 50 59 67
#> 
#> [[4]]
#> [1] 48 64 67
#> 
#> attr(,"cost")
#> [1] 27.22257
```