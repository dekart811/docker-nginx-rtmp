# nginx-rtmp

Alpine based nginx with the rtmp module for live multimedia streaming.

## Description

This image can be used to host an rtmp server for multimedia streaming using nginx and it's rtmp module.

The main purpose of this image is to use it for streaming from [OBS Studio](https://obsproject.com/) to your local network.

## How to use

```docker run -d -p 1935:1935 dekart811/nginx-rtmp```

## How to test with OBS Studio and VLC

* Start the container
* Open OBS Studio
* Goto *Settings -> Stream*
* Select *Custom* for *Service*
* In the *Server* field enter `rtmp://<ip_of_host>/live` replacing `<ip_of_host>` with the IP of the host where your container is running, e.g. `rtmp://192.168.0.10/live`
* In the *Stream Key* field enter something unique that will be used later in the client url to display that specific stream, e.g. `stream01`
* Start your stream
* Open VLC player and select *Media -> Open Network Stream*
* Enter the client url `rtmp://<ip_of_host>/live/<streamkey>`, e.g. `rtmp://192.168.0.10/live/stream01` and select *Play*
* You should now be able to watch your stream.