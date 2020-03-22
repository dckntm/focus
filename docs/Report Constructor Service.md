# Report Constructor Service 

**Report Constructor Service** is a micvroservice that is responsible for managing `Report Template`s. Currently it can:

* Create new `Report Template`
* Return short info about existing `Report Template`s
* Return entire `Report Template` model

## REST Configuration

After [launching service with docker](#how-to-deploy-with-docker) you can navigate to the following endpoints:

```
@url = http://localhost:5000

###

POST {{url}}/api/report/template HTTP/1.1
Content-Type: : application/json

{
  "report" : {
    "Id": "",
    "Title": "Title",
    "Questionnaires": [
      {
        "Sections": [
          {
            "Title": null,
            "Order": 0,
            "Repeatable": false,
            "Questions": [
              { "QuestionText": "question 1", "InputType": 6 },
              { "QuestionText": "question 2", "InputType": 10 }
            ]
          }
        ],
        "Title": null,
        "Order": 0
      }
    ],
    "Tables": []
  }
}

###

GET {{url}}/api/report/template/info HTTP/1.1

###

GET {{url}}/api/report/template/c19b4b52-bd4e-404e-8237-1317eb34859a HTTP/1.1
```

This `.rest` file for tests can be found as `tests/rest/report-constructor-api.rest` in [focus-backend](https://github.com/dckntm/focus-backend)

## How to deploy with Docker

Firstly be sure that your computer is prepared

1. Install Docker for you operating system
2. Ensure you have good internet connection
3. For VS Code users it will be worth installing official [Docker Extension](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-docker)
4. Ensure that Docker is up & running

Open in new VS Code window `src/Focus.Service.ReportConstructor/`

Run `docker-compose -f docker-compose.dev.yml up`

If something goes wrong see logs in terminal & work in separated editor
