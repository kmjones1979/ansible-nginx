## Variables for ansible|nginx configuration

#### global nginx / nginx plus variables

 | nginx_install_method: 				| method to install "package", "source" or "plus"
 | nginx_source_version: 				| version to compile of Nginx F/OSS 
 						  	note: Nginx Plus cannot be compiled and must be installed from a system repository
 
 | destination_host_os: 				| destination operating system that nginx will be deployed to ("ubuntu" or "centos")
 						  	currently only ubunutu method working, centos is planned 
 | destination_host_os_version: 			| operating system version
 
 | nginx_plus_default_site: 				| whether or not to enable the nginx plus default site template ("yes" or "no")
 | nginx_default_site:					| whether or not to enable the nginx default site template ("yes" or "no")
 
 | rabbitmq_install:					| whether or not to install rabbitmq for testing tcp load balancing ("yes" or "no") 
 | rabbitmq_version:					| which version of rabbitmq to install
 
 | nginx_user:						| user account which nginx should run
 | nginx_group:						| group for which the user nginx should be a member of
 | nginx_uid:						| default uid used during account creation
 | nginx_gid:						| default gid used during group creation

 | nginx_dir:						| nginx install directory
 | nginx_www_dir:					| default nginx web content directory
 | nginx_log_dir:					| default nginx log directory
 | nginx_pid:						| default location of nginx pid file
 | nginx_default_root:					| nginx default web root directory for default site
 | 
#### | nginx.conf variables |

| nginx_worker_processes:				| default number of worker_process spawned with nginx ("auto" reccommended)
| nginx_daemon_disable:				| enable or disable the nginx daemon ("yes" or "no")
| nginx_worker_rlimit_nofile:			| worker_rlimit_nofile value (set to null to ignore)
| nginx_error_log_options:			| nginx error log option flags
| nginx_error_log_level:				| nginx error log level ("info", "warn", "error" etc...)
| nginx_error_log_filename:			| nginx error log filename
| nginx_worker_connections:			| specify the number of worker connections
| nginx_multi_accept:				| enable or disable multi_accept ("yes" or "no")
| nginx_tcp_nodelay:				| enable or disable tcp_nodelay ("on" or "off")
| nginx_tcp_nopush:				| enable or disable tcp_nopush ("on" or "off")
| nginx_event:					| config value of events
| nginx_charset:					| specify what charset nginx should use
| nginx_disable_access_log:			| enabled disable the nginx access log ("on" or "off")
| nginx_server_tokens:				| enable or disable emitting nginx version in error messages and in server response header field ("on" or "off")
| nginx_sendfile:					| enable or disable sendfile ("on" or "off")
| nginx_keepalive:				| specify the keepalive_disable value
| nginx_keepalive_timeout:			| specify the keepalive timeout
| nginx_client_body_timeout:			| specify the timeout for reading client request body
| nginx_client_header_timeout:			| specify the timeout for reading the client request header
| nginx_send_timeout:				| specify the timeout for transmitting a response to the client
| nginx_buffers:					| enable or disable nginx buffer configuration in the template ("on" or "off")
| nginx_client_body_buffer_size:			| specify the client body buffer size
| nginx_client_header_buffer_size:		| specify the header buffer size
| nginx_client_max_body_size:			| specify the client max body size
| nginx_large_client_header_buffers:		| specify the number and size of client header buffers
| nginx_server_names_hash_bucket_size:		| specify the size of the server names hash bucket
| nginx_types_hash_max_size:			| specify the max size of the server names hash table
| nginx_types_hash_bucket_size:			| specify the max bucket size of the hash table
| nginx_proxy_read_timeout:			| specify the proxy read timeout
| nginx_enable_rate_limiting:			| enable or disable rate limiting in nginx
| nginx_rate_limiting_zone_name:			| specify the name of the rate limiting zone
| nginx_rate_limiting_backoff:			| specify the rate limiting backoff
| nginx_rate_limit:				| specify the nginx rate limit
| nginx_access_logs:				| access log variables name, format of the log, the filename and any options for the log

#### | source variables |

nginx_source_url:
nginx_source_prefix:
nginx_source_conf_path:
nginx_source_sbin_path:
nginx_source_default_configure_flags:

nginx_source_modules_included:
  http_stub_status_module:
  http_ssl_module:
  openssl:
  http_gzip_static_module:
  upload_progress_module:
  headers_more_module:
  http_auth_request_module:
  http_echo_module:
  google_perftools_module:
  ipv6_module:
  http_real_ip_module:
  http_spdy_module:
  http_perl_module:
  naxsi_module:
  ngx_pagespeed:

nginx_source_modules_excluded:
  | mail_pop3_module
  | mail_imap_module
  | mail_smtp_module

nginx_source_configure_flags:

#### | module variables |

nginx_gzip: null
nginx_gzip_http_version: 1.1
nginx_gzip_comp_level: 2
nginx_gzip_proxied: expired no|cache no|store private auth
nginx_gzip_vary: 'on'
nginx_gzip_buffers: null
nginx_gzip_min_length: 10240
nginx_gzip_types:
  | text/plain
  | text/css
  | text/xml
  | text/csv
  | text/javascript
  | application/x|javascript
  | application/xml
  | application/xml+rss
  | application/javascript
  | application/postscript
  | application/pdf
  | application/ecmascript
  | application/json
  | image/svg+xml
nginx_gzip_disable:


nginx_remote_ip_var:
nginx_authorized_ips:
  | "subnet"

nginx_gzip_static:


nginx_upload_progress_version:
nginx_upload_progress_javascript_output:
nginx_upload_progress_zone_name:
nginx_upload_progress_zone_size:
nginx_upload_progress_url:


nginx_headers_more_version:
nginx_headers_more_url:


nginx_auth_request_release:
nginx_auth_request_url:


nginx_echo_version:
nginx_echo_url:


nginx_realip_header:
nginx_realip_addresses:
nginx_realip_real_ip_recursive:


nginx_naxsi_version:
nginx_naxsi_url:

nginx_ngx_pagespeed_version:

openssl_version:


#### Nginx Plus variables... this area defines the variables for an example nginx plus load balancer configuration

nginx_plus_health_check_name:					| name of the healtcheck defined in nginx.conf
nginx_plus_health_check_reverse_check:				| enable or disable reverse checking !=
nginx_plus_health_status_match:					| http code to match on response
nginx_plus_health_header_content:				| health check content type
nginx_plus_health_regex:					| regex healthcheck match
nginx_plus_health_body_match:					| health check matching string

#### variables for defining an example listen directive for running a backend nginx server

nginx_plus_default_example_enabled:				| enable or disable the default example site ("yes" or "no")
nginx_plus_default_example_listen_port:				| port for the default site to listen on
nginx_plus_default_server_name:					| server name for the default site
nginx_plus_default_status_zone: 				| status zone name for default site
nginx_plus_default_location_path:				| default location path for site
nginx_plus_default_root_path:					| root path for nginx web directory
nginx_plus_default_index_types:					| default index file names
nginx_plus_default_status_json:					| enable or disable the status json feed ("yes" or "no")
nginx_plus_default_status_allow:				| specify the allow for the status json feed (set to null to ignore)
nginx_plus_default_status_deny:					| specify the deny for the status json ("all" or null to ignore)

#### variables for defining an example upstream with advanced configuration options in nginx.conf

nginx_plus_upstream_name:					| upstream name for template example
nginx_plus_upstream_resolver:					| resolver to specify dns lookups
nginx_plus_upstream_resolver_valid:				| specify how long a dns resolution is good for "ttl"
nginx_plus_upstream_resolver_enable_ipv6:			| enable ipv6 for the resolver
nginx_plus_upstream_resolver_timeout:				| set the resolver timeout for the upstream
nginx_plus_upstream_lb_method:					| set the load balancing method for the upstream (null to set default of round|robin)
nginx_plus_upstream_least_time_check:				| enable least|time
nginx_plus_upstream_hash_consistent:				| enable hash consistent
nginx_plus_upstream_zone:					| specify the upstream zone name
nginx_plus_upstream_zone_size:					| specify the upstream zone size
nginx_plus_upstream_server1:					| specify upstream server1
nginx_plus_upstream_server1_role:				| set the role of server1 (null to ignore)
nginx_plus_upstream_server1_max_conns:				| set the max connections of server1 (null to ignore)
nginx_plus_upstream_server1_max_fails:				| set the max fails of server1 (null to ignore)
nginx_plus_upstream_server1_max_fails_timeout:			| set the max fails timeout of server1 (null to ignore)
nginx_plus_upstream_server1_weight:				| set the weight of server1 (null to ignore)
nginx_plus_upstream_server1_force_resolve:			| set dns resolve to forced (null to ignore)
nginx_plus_upstream_server2:					| same
nginx_plus_upstream_server2_role: 				| same
nginx_plus_upstream_server2_max_conns:				| same
nginx_plus_upstream_server2_max_fails:				| same
nginx_plus_upstream_server2_max_fails_timeout:			| same
nginx_plus_upstream_server2_weight:				| same
nginx_plus_upstream_server2_force_resolve:			| same
nginx_plus_upstream_conn_queue:					| specify the conn queue for upstream
nginx_plus_upstream_conn_queue_timeout:				| specify the timeout for the conn queue
nginx_plus_upstream_keepalive:					| enable or disable upstream keepalive
nginx_plus_upstream_keepalive_num:				| specify the number of keepalive
nginx_plus_upstream_keepalive_single:				| specify the sinlge flag for keepalive in the upstream

#### variavles for defining upstream persistence configurations if needed

nginx_plus_upstream_enable_cookie: null
nginx_plus_upstream_cookie_name: null
nginx_plus_upstream_cookie_expires: null
nginx_plus_upstream_cookie_domain: null
nginx_plus_upstream_cookie_path: null
nginx_plus_upstream_sticky_http_only: null
nginx_plus_upstream_sticky_secure: null
nginx_plus_upstream_sticky_route: null
nginx_plus_upstream_sticky_learn: null
nginx_plus_upstream_sticky_learn_create: null
nginx_plus_upstream_sticky_learn_lookup: null
nginx_plus_upstream_sticky_learn_zone: null
nginx_plus_upstream_sticky_learn_timeout: null

#### default global proxy cache configurations

nginx_plus_global_proxy_cache_path: "/tmp/cache"
nginx_plus_global_proxy_cache_path_name: "mycache"
nginx_plus_global_proxy_cache_keys_zone: "mycache:10m"
nginx_plus_global_proxy_cache_inactive: "60m"
nginx_plus_global_map_proxy_cache_purge_enabled: "yes"
nginx_plus_global_map_proxy_cache_purge: "1"
nginx_plus_global_map_proxy_cache_default: "0"

#### default server block proxy cache configurations

nginx_plus_status_block_enabled: "yes"
nginx_plus_status_sb_listen_port: "9000"
nginx_plus_status_sb_status_zone: "status_dashboard"
nginx_plus_status_sb_root: "/usr/share/nginx/html"
nginx_plus_status_sb_location: "/status.html"
nginx_plus_status_sb_status_json: "yes"
nginx_plus_status_sb_status_allow: null
nginx_plus_status_sb_status_deny: null

#### default server block which will server / with http content to the upstream defined above

nginx_plus_default_sb_listen_port: "80"
nginx_plus_default_sb_status_zone: "nginx|plus_external"
nginx_plus_default_sb_server_name: "localhost"
nginx_plus_default_sb_location: "/"
nginx_plus_default_sb_set_host_header: "$host"
nginx_plus_default_sb_set_real_ip: "$remote_addr"
nginx_plus_default_sb_set_x_forwarded: "$proxy_add_x_forwarded_for"
nginx_plus_default_sb_proxy_pass: "http://nginx|plus_80"
nginx_plus_default_sb_proxy_cache: "mycache"
nginx_plus_default_sb_health_check: "yes"
nginx_plus_default_sb_health_interval: "10"
nginx_plus_default_sb_health_fails: "3"
nginx_plus_default_sb_health_passes: "2"
nginx_plus_default_sb_health_match_uri: "/index.html"
nginx_plus_default_sb_health_match_name: "health_chk"
nginx_plus_default_sb_status_json: "yes"
nginx_plus_default_sb_status_allow: null
nginx_plus_default_sb_status_deny: null
nginx_plus_default_sb_upstream_conf: "yes"
nginx_plus_default_sb_upstream_allow: "45.55.8.217"
nginx_plus_default_sb_upstream_deny: "all"

#### default tcp server block (rabbitmq)

nginx_plus_default_tcp_block_enabled: "yes"
nginx_plus_default_tcp_listen_port: "7000"
nginx_plus_default_tcp_status_zone: "rabbitmq"
nginx_plus_default_tcp_proxy_pass: "rabbitmq_7000"
nginx_plus_default_tcp_upstream_name: "rabbitmq_7000"
nginx_plus_default_tcp_zone_name: "rabbitmq"
nginx_plus_default_tcp_zone_size: "64k"
nginx_plus_default_tcp_server1: "127.0.0.1:5672"

