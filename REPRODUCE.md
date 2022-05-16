# Reproduction

* target: Trec-DL Document Ranking task (ANCE is 1st stage retrieval for SocialFormer)
* used poetry for dependency management + Python 3.9.7
* dependencies in setup.py vastly insufficient (missing pandas, torch, sklearn, tensorboard, ...)
* distributed launch not available in our cluster
* `run_ann_data_gen.py`: `model.module.query_emb(...)` incorrect, there is no attribute `module` in objects of this class
* downloaded checkpoint [Doc MaxP](https://webdatamltrainingdiag842.blob.core.windows.net/semistructstore/OpenSource/Document_ANCE_MaxP_Checkpoint.zip)
* unzipped in `model/checkpoint`, renamed to remove whitespaces, used the folder as `pretrained_checkpoint_dir`
* Use 32+ CPU cores for preprocessing, it is using multiprocessing with hardcoded value of 32