# scancode-plugins
Plugins for Running scancode on RoCm

# To Install the Plugins
Go to the Plugin Directory
'''cd scancode-toolkit/plugins/scancode-licence-modifications'''

### Run following command
 '''pip install -e .'''


### Example : 

'''scancode -clpeui  --package --processes 64 --license-text --verbose --full-root --json-pp roctracer.json ../roctracer --license-policy ../amd_licence_policy.yml --classify --summary --summary-with-details  --license-diag --no-licenses --licence-modifications'''


### To Create HTML reporved of approved, not approved and license modification html report


### scancode -clpeui --package --processes 64 --classify --verbose --full-root --json-pp roctracer.json ../roctracer --liceicy ../amd_licence_policy.yml --summary --summary-with-details --license-text --license-text-diagnostics --is-license-text --license-diag --no-licenses --licence-modifications --custom-output white-black-report.html --custom-template white-black-template.html

scancode -clpeui  --package --processes 64 --classify --keywordsscan --verbose --full-root --json-pp roctracer.json ../roctracer  --license-policy ../amd_licence_policy.yml  --summary --summary-with-details --license-text --license-text-diagnostics --is-license-text  --license-diag --licence-modifications --custom-output license-modification-list.html --custom-template license-modification-template.html


cancode  -clpeui  --package --processes 64 --classify --keywordsscan --verbose --full-root --json-pp rocrinfo.json /src/rocrinfo --license-policy ./amd_licence_policy.yml --summary --summary-with-details --license-text --license-text-diagnostics --is-license-text  --license-diag  --no-licenses  --licence-modifications --custom-output license-modification-list.html --custom-template license-modification-template.html | while IFS= read -r line; do printf '%s %s\n' "$(date)" "$line"; done > /logs/$(date "+%Y.%m.%d-%H.%M.%S")-logfile






### To check the overall status
Run scancodestatus.py with json results

For example : 
scancodestatus.py roctracer.json


