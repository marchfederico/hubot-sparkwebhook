# Hubot Cisco Spark Adapter

## Description

This is a [Cisco Spark](http://www.ciscospark.com) adapter for hubot that uses Cisco Spark
webhooks.

## Installation

* Follow the [Getting Started With Hubot](https://hubot.github.com/docs/) guide to get a local installation of Hubot
* Run the command `yo hubot` and when asked for an adapter, use "sparkwebhook"
* Create an outgoing "all events" webhook that points to your hubot instance ex. (http://myhubot_url:8080/hubot/ciscospark/incoming)
* Set the environment variable CISCOSPARK_ACCESS_TOKEN to your bot's access token.

## Example Installation

  ```sh

npm install -g yo generator-hubot

yo hubot --adapter sparkwebhook

curl -X POST -H "Authorization: Bearer YmQ5Mjk2YjUtM2FlNy00ZGU02Y5mZGEtY2I1OTQ5YzcyOTg4MzYTTTQ3OTktYjMw" -H "Content-Type: application/json"  -d '{
      "name": "hubot",
      "targetUrl": "http://myhubot:8080/hubot/ciscospark/incoming",
      "resource": "all",
      "event": "all"
}' "https://api.ciscospark.com/v1/webhooks"

export CISCOSPARK_ACCESS_TOKEN=YmQ5Mjk2YjUtM2FlNy00ZGU02Y5mZGEtY2I1OTQ5YzcyOTg4MzYTTTQ3OTktYjMw

bin/hubot -a sparkwebhook
  ```


## Environment variables


This adapter uses the following environment variables:

**CISCOSPARK_ACCESS_TOKEN** (required)

The token that [Spark for Developers Portal](https://developer.ciscospark.com/apps.html) gives you when creating a bot account
