#!/bin/bash

# Dependencies: streamlink, curl
#
# Description: Polls twitch channel status and downloads stream if user is online
# Get your Client-ID - https://dev.twitch.tv/docs/v5

clientid=''

# Records only!!! one!!! stream from the list
# can run multiple copies of the script using screen
Usage="$0 <space-separated list of twitch channels>"

Channels=($@)
Interval="5" # polling interval in seconds

if [[ -z "$Channels" ]]; then
  echo "Error: No channels provided"
  echo "Usage: $Usage"
  exit 1
fi

while true; do
  for i in ${Channels[@]}; do
    StreamData="$(curl -s  "https://api.twitch.tv/kraken/streams/$i" -H "Client-ID: $clientid")"
    if echo "$StreamData" | grep -q '"status":404'; then # 404 Error
      echo "Error: $i does not exist."
      break 2
    elif echo "$StreamData" | grep -q '"stream":null'; then # Channel offline
      echo "$i is offline."
    else # Channel online
      echo "$i is live. Downloading stream..."
    streamlink --hls-segment-threads=5 --twitch-disable-hosting "http://www.twitch.tv/$i" 1080p60,1080p,900p60,900p,720p60,720p -o "$HOME/vods/${i}-$
    fi
  done
  sleep "$Interval"
done
