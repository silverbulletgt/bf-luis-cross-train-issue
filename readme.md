Starting in the directory root directory
Run the command: bf luis:cross-train -i Application -o application/cross-trained-sub-folder --config application/cross-train.config.json --force

This will output the files to ../Application/cross-trained

Notice that the utterances / QnA pairs from the external files which are referenced are not included.
Also the ExternalFile.lu & ExternalFile.qna files are not included in the application/cross-trained-sub-folder folder

Starting in the directory the root directory
Run the command: bf luis:cross-train -i . -o Application/cross-trained-root-folder --config Application/cross-train.config.json --force

This will output the files to ../Application/cross-trained

Notice that the utterances / QnA pairs from the external files which are referenced are included
Also the ExternalFile.lu & ExternalFile.qna files are included in the application/cross-trained-sub-folder folder

