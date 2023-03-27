# Helm Chart update process for Redis can be completed using kpt or manually by merging the upstream chart with our chart.

# Recommended testing approach for Redis package upgrades
1) Once helm chart is updated with upstream, push your renovate branch to Repo1
2) Since Bigbang umbrella does not deploy Redis as a package, we can deploy Redis as part of AuthService package. Create a branch on AuthService package repo.
3) Helm Package your local Redis chart and copy to the AuthService branch under authservice/chart/charts/redis.x.tgz
4) Push AuthService branch to repo1
5) Modify your BB values to use the AuthService git branch that you pushed to repo1.
6) Deploy Bigbang with Monitoring and AuthService packages enabled. Set AuthService, Redis enabled to true. Deploy with SSO enabled.
7) Login to Grafana and check for Redis dashboards. Verify data is received. 
8) Login to Prometheus and Alert Manager using SSO. These logins use the AuthService which will rely on Redis for session persistence if Redis is enabled.
9) Pull logs for AuthService controller, verify connection to Redis is established. Output should be seen in logs.
10) Pull logs for AuthService Redis Master pod, verify connection from master to replica pods is successful. Output should be seen in logs.
11) Cleanup/Delete your AuthService branch