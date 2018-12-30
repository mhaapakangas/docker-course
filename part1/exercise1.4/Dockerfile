FROM ubuntu:16.04

WORKDIR /mydir
RUN apt-get update && apt-get install -y curl

RUN echo '#!/bin/bash\nread website; sleep 3; curl http://$website;' > script.sh
RUN chmod u+x script.sh
CMD ["/mydir/script.sh"]
