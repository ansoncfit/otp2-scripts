# otp2-scripts
 Example scripts for batch queries to an OpenTripPlanner v2 server

 The `OTP2-batch.ipynb` notebook will write a CSV of walk/transit travel times for specified origin-destination pairs. Other tools (e.g. [R5](https://github.com/conveyal/r5)) may be much faster, especially for full O-D travel time matrices.

## Setup

Download OTP2 .jar (available [here](https://repo1.maven.org/maven2/org/opentripplanner/otp/)).

Modify `conf/build-config.json` so that the service dates correspond with the GTFS you will use.

Copy GTFS (.zip), OSM (.pbf), and `build-config.json` to a single directory (e.g. `graph`)

Start OTP2: `java -jar -Xmx6G otp-2.0.0.jar --build --save --serve graph`. If you've built a graph previously (i.e. `graph.obj` is present in the target directory): `java -jar -Xmx6G otp-2.0.0.jar --load graph`.

Modify `conf/routingRequest.json` so that it has desired parameters.

Save origin and destination .csv files, each with columns `GEOID, X, Y`, to the `conf` directory.

Open and run the `OTP2-batch.ipynb` notebook in jupyter lab.