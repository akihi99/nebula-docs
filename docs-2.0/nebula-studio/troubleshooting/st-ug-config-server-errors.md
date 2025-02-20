# Connecting to the database error

## Problem description

According to the [connect Studio](../deploy-connect/st-ug-connect.md) operation, it prompts **failed**.

## Possible causes and solutions

You can troubleshoot the problem by following the steps below.

### Step1: Confirm that the format of the **Host** field is correct

You must fill in the IP address (`graph_server_ip`) and port of the NebulaGraph database Graph service. If no changes are made, the port defaults to `9669`. Even if NebulaGraph and Studio are deployed on the current machine, you must use the local IP address instead of `127.0.0.1`, `localhost` or `0.0.0.0`.

### Step2: Confirm that the **username** and **password** are correct

If authentication is not enabled, you can use root and any password as the username and its password.

If authentication is enabled and different users are created and assigned roles, users in different roles log in with their accounts and passwords.

### Step3: Confirm that NebulaGraph service is normal

Check NebulaGraph service status. Regarding the operation of viewing services:

- If you compile and deploy NebulaGraph on a Linux server, refer to the [NebulaGraph service](../../4.deployment-and-installation/2.compile-and-install-nebula-graph/deploy-nebula-graph-cluster.md).

- If you use NebulaGraph deployed by Docker Compose and RPM, refer to the [NebulaGraph service status and ports](../deploy-connect/st-ug-deploy.md).

If the NebulaGraph service is normal, proceed to Step 4 to continue troubleshooting. Otherwise, please restart NebulaGraph service.

!!! Note

    If you used `docker-compose up -d` to satrt NebulaGraph before, you must run the `docker-compose down` to stop NebulaGraph.

### Step4: Confirm the network connection of the Graph service is normal

Run a command (for example, telnet <graph_server_ip> 9669) on the Studio machine to confirm whether NebulaGraph's Graph service network connection is normal.

If the connection fails, check according to the following steps:

- If Studio and NebulaGraph are on the same machine, check if the port is exposed.

- If Studio and NebulaGraph are not on the same machine, check the network configuration of the NebulaGraph server, such as firewall, gateway, and port.

If you cannot connect to the NebulaGraph service after troubleshooting with the above steps, please go to the [NebulaGraph forum](https://discuss.nebula-graph.io) for consultation.