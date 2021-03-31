This repo demonstrates an issue with the bf luis:cross-train command.

The issue is that if you have a .lu or .qna file which references an external file which is in a folder above the folder specified in the -i parameter or above the current folder when -i is the current folder (.) then the intent / utterances / qna question answer pair are not included in the cross trained .lu & .qna files.
This functionality works as expected when the external files are in or below the folder specified in -i parameter or the current folder when -i is the current folder (.)

To replicate this issue:
Starting in the directory root directory
Run the command: bf luis:cross-train -i Application -o application/cross-trained-sub-folder --config application/cross-train.config.json --force

This will output the files to ../Application/cross-trained-sub-folder

Notice that the utterances / QnA pairs from the external files which are referenced are not included.
Also the ExternalFile.lu & ExternalFile.qna files are not included in the application/cross-trained-sub-folder folder

To show what is the expected output:
Starting in the directory the root directory
Run the command: bf luis:cross-train -i . -o Application/cross-trained-root-folder --config Application/cross-train.config.json --force

This will output the files to ../Application/cross-trained-root-folder

Notice that the utterances / QnA pairs from the external files which are referenced are included
Also the ExternalFile.lu & ExternalFile.qna files are included in the application/cross-trained-sub-folder folder

