#Multiple Jest Test Result Processors ![npm](https://img.shields.io/npm/v/jest-multiple-result-processors.svg)

![CircleCI token](https://img.shields.io/circleci/token/5efb6fd44edda4c2dba4ef86fa3502b95df20ebc/project/github/meza/jest-multiple-result-processors/master.svg?label=circleci)
[![codecov](https://codecov.io/gh/meza/jest-multiple-result-processors/branch/master/graph/badge.svg)](https://codecov.io/gh/meza/jest-multiple-result-processors)
![Dependencies](https://david-dm.org/meza/jest-multiple-result-processors.svg)
[![install size](https://packagephobia.now.sh/badge?p=jest-multiple-result-processors)](https://packagephobia.now.sh/result?p=jest-multiple-result-processors)
[![npm downloads](https://img.shields.io/npm/dm/jest-multiple-result-processors.svg?style=flat-square)](http://npm-stat.com/charts.html?package=jest-multiple-result-processors)
![Snyk Vulnerabilities for npm package](https://img.shields.io/snyk/vulnerabilities/npm/jest-multiple-result-processors.svg)
![NPM](https://img.shields.io/npm/l/jest-multiple-result-processors.svg)


Jest currently has no capabilities of chaining multiple test result processors out of the box.

[There is an issue raised on the official github of Jest](https://github.com/facebook/jest/issues/4479), but it seems to
not bare any fruit. The solution in that thread is to create your own processor which chains together the processors you 
need. 

This small utility does just that.

## Install

```
yarn add -D jest-multiple-result-processors
```

```
npm install --dev jest-multiple-result-processors
```

## Configure

You have to tell Jest to use this library as its main test result processor.
In addition to that, you need to configure this library and list all the modules you want to run on the test result.
If the ordering matters (which I advise against), the results will be threaded through from top to bottom.

###package.json
```json
{
  "jestTestResultProcessors": [
    "test-result-processor-module-1",
    "./your-custom-processor.js"
  ],
  "jest": {
    "testResultsProcessor": "jest-multiple-result-processors"
  }
}

```

## Disclaimer
This is the first draft of this package, feel free to submit changes.
