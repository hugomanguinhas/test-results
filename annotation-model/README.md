Annotation Model test results
=============================

Up-to-date result reports are available at:

* https://w3c.github.io/test-results/annotation-model/all.html
* https://w3c.github.io/test-results/annotation-model/less-than-2.html
* https://w3c.github.io/test-results/annotation-model/complete-fails.html

Index of implementations in reports
===================================

* EB - implementation Name: Emblematica Online (Developmental Version)
  * email: mjsarol@illinois.edu
  * link: http://emblematica.library.illinois.edu/portal_anno/
  * gitHub: not yet

* HY - implementation Name: Hypothesis
  * email: dev@list.hypothes.is
  * link: https://hypothes.is
  * gitHub: https://github.com/hypothesis

* TK - implementation Name: Takeshi Kanai
  * email: takeshi.kanai@sony.com
  

Adding new results
==================

To add new tests results:

1. For each category of annotation that your implementation can generate, produce a JSON test result file using http://w3c-test.org/tools/runner/index.html?path=/annotation-model/annotations/ (soon), or http://testdev.spec-ops.io:8000/tools/runner/index.html?path=/annotation-model/annotations/ (working now), or your local, up to date clone of https://github.com/w3c/web-platform-tests.
  * Be sure to specify `/annotation-model/annotations/` as the path for which tests to run.
  * Click start and 3 HTML Web forms listing different test assertions will be displayed sequentially in a new window. For each form, you will prompted to provide (paste into a text box) the JSON serialization of the annotation from your implementation that you want to test; enter the same annotation into each of the 3 forms. (To test a second or subsequent annotation, you must run the complete test again, all 3 forms.)
  * After the third HTML completes and closes, be sure to click the `Download JSON results` button to retrieve and save your JSON test results file.
  * Please test and submit the fewest annotations and test-results required to demonstrate the full range of annotation model features your annotation client implements. In other words only test and submit results for a second annotation if the second annotation includes one or more model features not found in the first annotation you tested, for example, if your annotation 01 includes the bodyValue key and your annotation 02 includes the body key instead. Only include a 3rd annotation if it includes one or more features not found in your first and second annotations. And so on.  
  * Note that failures to pass individual test assertions can be caused by the annotation not using that particular feature, and for the optional tests should not be cause for alarm.
2. Fork the w3c/test-results repo if you haven't already (https://github.com/w3c/test-results)
3. Select a unique two letter abbreviation for your implementation under test (e.g., AB) and add it to the 'Index of implementations in reports' in the /annotation-model/README.md file in your forked copy. Provide implementation name, contact email, Website (if publicly available), GitHub repository (if you have one). Use the information provided by previous implementations in the list as a model.
4. Rename your JSON test-results file using the two letter abbreviation you chose and a two digit number value representing annotation number used as input for that test run, for example, _AA00_.json.
5. Place your newly renamed results files in the annotation-model directory
6. Place copies of each annotation you tested in a subfolder named by concatenating your two letter abbreviation and the string '-input', e.g., _AA_-input/anno01.json
  * When naming your individual annotation files, please follow the convention illustrated of including 2 digits in the file name so that it is obvious which annotation goes with which test results file. 
6. Create a pull request with your updated files
7. When it is merged the maintainers will update the overall results reports automatically

If you want to see what your implementation test results reports would look like locally, use the wptreport tool (https://github.com/spec-ops/wptreport) to build a 
report with a command line like `wptreport -f -m -s "Annotation Model"`

