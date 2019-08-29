# Build image: image-sb-ubi8-sb-6.6.0.1-linux-2.6-x86_64:v8
docker build -f ua-redhat-dockerfile -t image-sb-ubi8-sb-6.6.0.1-linux-2.6-x86_64:v8 --build-arg ua_version=6.6.0.1 .

# Initiate Container: 
docker run --user 10011:0 -it -d --hostname=img-sb-ua --env-file=env_agent_file --name ua_demo image-sb-ubi8-sb-6.6.0.1-linux-2.6-x86_64:v8

# container log file
docker logs ua_demo

# enter the running container:
docker exec -it ua_sidecar_pod_cont /bin/bash


  INFO [logger] (/home/build1/release_builds/source/uag/uagsrv/headers/logshell.c:930) OPSTRC002I Log task is starting
   INFO [WMSLSNR] (wmnlsnr.c:3269) OPSAGT013I OpsWise WMSLSNR task initialization complete
   INFO [WMSFAHN] (wmnlsnr.c:1541) OPSAGT013I OpsWise WMSFAHN task initialization complete
   INFO [WMNMTSK] (wmnmtsk.c:2295) OPSAGT011I OpsWise MTSK queue obtained for Agent named: AGNT0077 to Core: ops.controller.queue
   INFO [WMNMTSK] (wmnmtsk.c:2296) OPSAGT028I OpsWise MTSK Netid: 7878@192.168.88.22
UAG1082I [1567069878] OMS connection ID ops.agent.AGNT0077 established with OMS server at 192.168.88.22:7878.
   INFO [WMNMTSK] (wmnmtsk.c:2316) OPSAGT002I A Queue was obtained for OpsWise Main task
   INFO [WMNMTSK] (wmnmtsk.c:2380) OPSAGT003I OpsWise MAIN task initialization complete
   INFO [WMNMTSK] (wmnmtsk.c:2502) OPSAGT029I OpsWise Warm Start successful. Found Jobs 0. Resumed 0. InDoubt 0. Found Applications 0.
   INFO [WNHEART] (wnheart.c:571) OPSAGT004I OpsWise Main task preparing to process work queues
   INFO [WNHEART] (wnheart.c:574) OPSAGT013I OpsWise WNHEART task initialization complete
   INFO [asiMainFunc] (wnasini.c:1031) OPSASI030I All tasks started, delaying 2.00 seconds
   INFO [cbHello] (wmnmtsk.c:1893) OPSTRC002I Negotiated authentication version: 2
   INFO [WNHBMON] (wnheart.c:265) OPSAGT020I OpsWise WMHBMON starting Hearbeats. Heartbeat Interval: 120.000000 seconds
   INFO [asiMainFunc] (wnasini.c:1040) OPSASI031I Monitoring subtask completions
   INFO [asiMainFunc] (wnasini.c:1046) OPSAGT022I OpsWise Agent Version 6.6.0.0 initialization completed
   INFO [asiMainFunc] (wnasini.c:1047) OPSASI016I PROD_BUILD: 236  BUILD_DATE: 20190329150316 
   INFO [asiMainFunc] (wnasini.c:1051) OPSAGT048I Transporter communication not configured for SSL.
   INFO [asiMainFunc] (wnasini.c:1060) OPSTRC002I FTP File Monitor Fault Tolerance is DISABLED
UAG1047I [1567069878] I,Universal Automation Center Agent 6.6.0 Level 0 Release Build 236 Date 20190329150316 started.
   INFO [asiMainFunc] (wnasini.c:1096) OPSASI012I Main task initialization completed, waiting for messages. Agent ID: AGNT0077, Msghub ID: ops.controller.queue, Transports: 7878@192.168.88.22.

