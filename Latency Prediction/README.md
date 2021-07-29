
We have latency data between different AWS cloud regions (they are included in src_dest_df.pkl). The locations of each AWS region is in region_geo_lookup_aws.pkl
- Predict the latency from AWS.ap-east-1 to all other AWS regions in the src_dest_df.parquet
- Next phase detect any time series anomalies / trends 

Data description: 
intv_src_dest_df.parquet
timestamp              datetime64[ns, UTC] -> when the latency measurements was taken
cloud_geo_iso1                      object -> source cloud region doing the ping
cloud_geo_iso2                      object -> destination cloud region doing the ping
latency_ms                         float64 -> latency in milliseconds between the src and destination region
packet_loss_percent                float64 -> packet loss in percentage between the src and dest region 

region_geo_lookup_aws.pkl
region_name                object -> cloud region name (would correspond to cloud_geo_iso1 or cloud_geo_iso2 from above)
cloud_service_provider     object -> ignore 
city_name                  object -> city/country where the region is located 
lat                       float64 -> latitude of the region 
lon                       float64 -> longitude of the region 
timestamp                  object -> ignore 
