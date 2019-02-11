Have to debug why statsd is not working from your docker container?

Try these:

Check to see if statsd is listening
`sudo lsof -i | grep 8125`

See if traffic is flowing from docker
`sudo /usr/sbin/tcpdump -n -i docker0 'port 8125'`

Listen on port on localhost inside container to see if traffic is not configured
properly:
`sudo docker exec -it <container_id> nc -lk -u -p 8125`
