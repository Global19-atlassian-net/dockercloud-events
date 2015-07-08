tutum/events
============

System container that forwards docker events to Tutum's API. System containers are launched, configured and managed automatically on every node by Tutum.


## Usage

    docker run \
      -d \
	  -v /usr/lib/tutum/docker:/usr/bin/docker
      -v /var/run:/var/run:rw \
      -e TUTUM_URL=xxxxxxxx
      [-e SENTRY_DSN=xxxxxxxx] \
      [-e REPORT_INTERVAL=30] \
      tutum/events


## Arguments

Key | Description
----|------------
TUTUM_AUTH | Tutum's API role `Authorization` header
TUTUM_UTL  | The URL that docker events are POSTed to 
SENTRY_DSN | (optional) Sentry DSN for bug reporting
REPORT_INTERVAL | (optional) Interval in seconds to report autorestarted container events
