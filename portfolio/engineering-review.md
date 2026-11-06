# Dragon Forge · engineering release review

**Decision: keep the integration and hold creative acceptance.** The pilot recovered completed work after a restart and produced a decodable sequence. Character consistency and required-audio quality still needed work. Those are separate acceptance decisions.

![Frames immediately before and after a shot boundary](frame-handoff.webp)

*Two frames from the pilot evidence, shown side by side at a cut. A close handoff is useful evidence for this transition. It cannot establish that identity stays consistent throughout either shot.*

## What the checks established

| Engineering question | Check and result | Release consequence |
|---|---|---|
| Can malformed input enter the pipeline? | The compiler refused a non-object input. A valid object reached ordinary validation. Healthy hardware-readiness records passed; incomplete or malformed records were rejected. | Check both refusal and acceptance. A validator that rejects everything would pass a negative-only test. |
| Can an upstream success hide a downstream failure? | Four malformed terminal-queue examples reproduced a weakness during review. | Track the polling defect separately from the passing readiness checks. |
| Did the change regress existing behavior? | The archived test run recorded **377 passed, 260 warnings**. A separate CPU replay recorded **38 legacy, 29 previously added, and 43 new cases**. | Keep older fixtures alongside new failure cases. Counts describe the recorded runs; they do not settle the open defects. |
| Does a restart repeat expensive work? | The first shot finished. After the dispatcher restarted, it recognized that shot and continued with the next two. A later trim reused existing media. | Recovery and trim reuse were demonstrated. General reuse after an arbitrary edit still needs a separate test. |
| Is the final file usable? | Review decoded six MP4s. The trimmed sequence contained **1,800 frames at 60 fps**, or 30 seconds. Two native audio tracks measured below the required floor. | Accept the duration check. Keep required-audio quality open; changing a label to “quiet” does not repair a track. |
| Can we trace the evidence? | Review matched seven delivered artifacts to their receipts and checked 161 payload hashes inside the evidence archive. | Use integrity checks to identify the files reviewed. Judge visual continuity by watching the shots. |

![Crop of the sequence displayed in the pilot playback panel](review-player.webp)

*Actual browser evidence, cropped to the playback viewport. The workflow canvas, prompts and internal run identifiers are outside the crop.*

## How I apply source grounding in RAG work

My Windows research workspace separated source PDFs, processed text, the index and query logs. A later learning project, Clip Knowledge Curator, illustrates what I mean by a traceable source: one RAG lesson record preserved **69 subtitle cues**, their timestamps, and references to the source clip and subtitle file. It also recorded where frames were sampled and which aspects of synchronization still needed verification.

| Example review question | Evidence I would use | Boundary |
|---|---|---|
| Where does the lesson introduce retrieval and generation? | My lesson record points to the opening **00:00–01:51** interval. A reviewer can go back to the segment and compare the summary with the source. | This illustrates source attribution. It is not a measured retrieval-accuracy score. |
| How accurately does the index retrieve the right passage? | A separate evaluation would need a set of queries, expected source passages, and observed retrieval results. | I have not published a retrieval benchmark for this workspace. |

[Back to the project timeline](../README.md)
