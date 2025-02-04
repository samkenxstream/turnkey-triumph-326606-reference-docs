---
title: kube-proxy Configuration (v1alpha1)
content_type: tool-reference
package: kubeproxy.config.k8s.io/v1alpha1
auto_generated: true
---


## Resource Types 


- [KubeProxyConfiguration](#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConfiguration)
  
    

## `ClientConnectionConfiguration`     {#ClientConnectionConfiguration}
    

**Appears in:**

- [KubeProxyConfiguration](#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConfiguration)

- [KubeSchedulerConfiguration](#kubescheduler-config-k8s-io-v1beta3-KubeSchedulerConfiguration)

- [KubeSchedulerConfiguration](#kubescheduler-config-k8s-io-v1beta2-KubeSchedulerConfiguration)

- [GenericControllerManagerConfiguration](#controllermanager-config-k8s-io-v1alpha1-GenericControllerManagerConfiguration)


<p>ClientConnectionConfiguration contains details for constructing a client.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
  
<tr><td><code>kubeconfig</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>kubeconfig is the path to a KubeConfig file.</p>
</td>
</tr>
<tr><td><code>acceptContentTypes</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>acceptContentTypes defines the Accept header sent by clients when connecting to a server, overriding the
default value of 'application/json'. This field will control all connections to the server used by a particular
client.</p>
</td>
</tr>
<tr><td><code>contentType</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>contentType is the content type used when sending data to the server from this client.</p>
</td>
</tr>
<tr><td><code>qps</code> <B>[Required]</B><br/>
<code>float32</code>
</td>
<td>
   <p>qps controls the number of queries per second allowed for this connection.</p>
</td>
</tr>
<tr><td><code>burst</code> <B>[Required]</B><br/>
<code>int32</code>
</td>
<td>
   <p>burst allows extra queries to accumulate when a client is exceeding its rate.</p>
</td>
</tr>
</tbody>
</table>

## `DebuggingConfiguration`     {#DebuggingConfiguration}
    

**Appears in:**

- [KubeSchedulerConfiguration](#kubescheduler-config-k8s-io-v1beta3-KubeSchedulerConfiguration)

- [KubeSchedulerConfiguration](#kubescheduler-config-k8s-io-v1beta2-KubeSchedulerConfiguration)

- [GenericControllerManagerConfiguration](#controllermanager-config-k8s-io-v1alpha1-GenericControllerManagerConfiguration)


<p>DebuggingConfiguration holds configuration for Debugging related features.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
  
<tr><td><code>enableProfiling</code> <B>[Required]</B><br/>
<code>bool</code>
</td>
<td>
   <p>enableProfiling enables profiling via web interface host:port/debug/pprof/</p>
</td>
</tr>
<tr><td><code>enableContentionProfiling</code> <B>[Required]</B><br/>
<code>bool</code>
</td>
<td>
   <p>enableContentionProfiling enables lock contention profiling, if
enableProfiling is true.</p>
</td>
</tr>
</tbody>
</table>

## `FormatOptions`     {#FormatOptions}
    

**Appears in:**

- [LoggingConfiguration](#LoggingConfiguration)


<p>FormatOptions contains options for the different logging formats.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
  
<tr><td><code>json</code> <B>[Required]</B><br/>
<a href="#JSONOptions"><code>JSONOptions</code></a>
</td>
<td>
   <p>[Experimental] JSON contains options for logging format &quot;json&quot;.</p>
</td>
</tr>
</tbody>
</table>

## `JSONOptions`     {#JSONOptions}
    

**Appears in:**

- [FormatOptions](#FormatOptions)


<p>JSONOptions contains options for logging format &quot;json&quot;.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
  
<tr><td><code>splitStream</code> <B>[Required]</B><br/>
<code>bool</code>
</td>
<td>
   <p>[Experimental] SplitStream redirects error messages to stderr while
info messages go to stdout, with buffering. The default is to write
both to stdout, without buffering.</p>
</td>
</tr>
<tr><td><code>infoBufferSize</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/api/resource#QuantityValue"><code>k8s.io/apimachinery/pkg/api/resource.QuantityValue</code></a>
</td>
<td>
   <p>[Experimental] InfoBufferSize sets the size of the info stream when
using split streams. The default is zero, which disables buffering.</p>
</td>
</tr>
</tbody>
</table>

## `LeaderElectionConfiguration`     {#LeaderElectionConfiguration}
    

**Appears in:**

- [KubeSchedulerConfiguration](#kubescheduler-config-k8s-io-v1beta2-KubeSchedulerConfiguration)

- [KubeSchedulerConfiguration](#kubescheduler-config-k8s-io-v1beta3-KubeSchedulerConfiguration)

- [GenericControllerManagerConfiguration](#controllermanager-config-k8s-io-v1alpha1-GenericControllerManagerConfiguration)


<p>LeaderElectionConfiguration defines the configuration of leader election
clients for components that can run with leader election enabled.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
  
<tr><td><code>leaderElect</code> <B>[Required]</B><br/>
<code>bool</code>
</td>
<td>
   <p>leaderElect enables a leader election client to gain leadership
before executing the main loop. Enable this when running replicated
components for high availability.</p>
</td>
</tr>
<tr><td><code>leaseDuration</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>leaseDuration is the duration that non-leader candidates will wait
after observing a leadership renewal until attempting to acquire
leadership of a led but unrenewed leader slot. This is effectively the
maximum duration that a leader can be stopped before it is replaced
by another candidate. This is only applicable if leader election is
enabled.</p>
</td>
</tr>
<tr><td><code>renewDeadline</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>renewDeadline is the interval between attempts by the acting master to
renew a leadership slot before it stops leading. This must be less
than or equal to the lease duration. This is only applicable if leader
election is enabled.</p>
</td>
</tr>
<tr><td><code>retryPeriod</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>retryPeriod is the duration the clients should wait between attempting
acquisition and renewal of a leadership. This is only applicable if
leader election is enabled.</p>
</td>
</tr>
<tr><td><code>resourceLock</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>resourceLock indicates the resource object type that will be used to lock
during leader election cycles.</p>
</td>
</tr>
<tr><td><code>resourceName</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>resourceName indicates the name of resource object that will be used to lock
during leader election cycles.</p>
</td>
</tr>
<tr><td><code>resourceNamespace</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>resourceName indicates the namespace of resource object that will be used to lock
during leader election cycles.</p>
</td>
</tr>
</tbody>
</table>

## `LoggingConfiguration`     {#LoggingConfiguration}
    

**Appears in:**

- [KubeletConfiguration](#kubelet-config-k8s-io-v1beta1-KubeletConfiguration)


<p>LoggingConfiguration contains logging options
Refer <a href="https://github.com/kubernetes/component-base/blob/master/logs/options.go">Logs Options</a> for more information.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
  
<tr><td><code>format</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>Format Flag specifies the structure of log messages.
default value of format is <code>text</code></p>
</td>
</tr>
<tr><td><code>flushFrequency</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/time#Duration"><code>time.Duration</code></a>
</td>
<td>
   <p>Maximum number of seconds between log flushes. Ignored if the
selected logging backend writes log messages without buffering.</p>
</td>
</tr>
<tr><td><code>verbosity</code> <B>[Required]</B><br/>
<code>uint32</code>
</td>
<td>
   <p>Verbosity is the threshold that determines which log messages are
logged. Default is zero which logs only the most important
messages. Higher values enable additional messages. Error messages
are always logged.</p>
</td>
</tr>
<tr><td><code>vmodule</code> <B>[Required]</B><br/>
<a href="#VModuleConfiguration"><code>VModuleConfiguration</code></a>
</td>
<td>
   <p>VModule overrides the verbosity threshold for individual files.
Only supported for &quot;text&quot; log format.</p>
</td>
</tr>
<tr><td><code>sanitization</code> <B>[Required]</B><br/>
<code>bool</code>
</td>
<td>
   <p>[Experimental] When enabled prevents logging of fields tagged as sensitive (passwords, keys, tokens).
Runtime log sanitization may introduce significant computation overhead and therefore should not be enabled in production.`)</p>
</td>
</tr>
<tr><td><code>options</code> <B>[Required]</B><br/>
<a href="#FormatOptions"><code>FormatOptions</code></a>
</td>
<td>
   <p>[Experimental] Options holds additional parameters that are specific
to the different logging formats. Only the options for the selected
format get used, but all of them get validated.</p>
</td>
</tr>
</tbody>
</table>

## `VModuleConfiguration`     {#VModuleConfiguration}
    
(Alias of `[]k8s.io/component-base/config/v1alpha1.VModuleItem`)

**Appears in:**

- [LoggingConfiguration](#LoggingConfiguration)


<p>VModuleConfiguration is a collection of individual file names or patterns
and the corresponding verbosity threshold.</p>



  
    

## `KubeProxyConfiguration`     {#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConfiguration}
    


<p>KubeProxyConfiguration contains everything necessary to configure the
Kubernetes proxy server.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
<tr><td><code>apiVersion</code><br/>string</td><td><code>kubeproxy.config.k8s.io/v1alpha1</code></td></tr>
<tr><td><code>kind</code><br/>string</td><td><code>KubeProxyConfiguration</code></td></tr>
    
  
<tr><td><code>featureGates</code> <B>[Required]</B><br/>
<code>map[string]bool</code>
</td>
<td>
   <p>featureGates is a map of feature names to bools that enable or disable alpha/experimental features.</p>
</td>
</tr>
<tr><td><code>bindAddress</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>bindAddress is the IP address for the proxy server to serve on (set to 0.0.0.0
for all interfaces)</p>
</td>
</tr>
<tr><td><code>healthzBindAddress</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>healthzBindAddress is the IP address and port for the health check server to serve on,
defaulting to 0.0.0.0:10256</p>
</td>
</tr>
<tr><td><code>metricsBindAddress</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>metricsBindAddress is the IP address and port for the metrics server to serve on,
defaulting to 127.0.0.1:10249 (set to 0.0.0.0 for all interfaces)</p>
</td>
</tr>
<tr><td><code>bindAddressHardFail</code> <B>[Required]</B><br/>
<code>bool</code>
</td>
<td>
   <p>bindAddressHardFail, if true, kube-proxy will treat failure to bind to a port as fatal and exit</p>
</td>
</tr>
<tr><td><code>enableProfiling</code> <B>[Required]</B><br/>
<code>bool</code>
</td>
<td>
   <p>enableProfiling enables profiling via web interface on /debug/pprof handler.
Profiling handlers will be handled by metrics server.</p>
</td>
</tr>
<tr><td><code>clusterCIDR</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>clusterCIDR is the CIDR range of the pods in the cluster. It is used to
bridge traffic coming from outside of the cluster. If not provided,
no off-cluster bridging will be performed.</p>
</td>
</tr>
<tr><td><code>hostnameOverride</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>hostnameOverride, if non-empty, will be used as the identity instead of the actual hostname.</p>
</td>
</tr>
<tr><td><code>clientConnection</code> <B>[Required]</B><br/>
<a href="#ClientConnectionConfiguration"><code>ClientConnectionConfiguration</code></a>
</td>
<td>
   <p>clientConnection specifies the kubeconfig file and client connection settings for the proxy
server to use when communicating with the apiserver.</p>
</td>
</tr>
<tr><td><code>iptables</code> <B>[Required]</B><br/>
<a href="#kubeproxy-config-k8s-io-v1alpha1-KubeProxyIPTablesConfiguration"><code>KubeProxyIPTablesConfiguration</code></a>
</td>
<td>
   <p>iptables contains iptables-related configuration options.</p>
</td>
</tr>
<tr><td><code>ipvs</code> <B>[Required]</B><br/>
<a href="#kubeproxy-config-k8s-io-v1alpha1-KubeProxyIPVSConfiguration"><code>KubeProxyIPVSConfiguration</code></a>
</td>
<td>
   <p>ipvs contains ipvs-related configuration options.</p>
</td>
</tr>
<tr><td><code>oomScoreAdj</code> <B>[Required]</B><br/>
<code>int32</code>
</td>
<td>
   <p>oomScoreAdj is the oom-score-adj value for kube-proxy process. Values must be within
the range [-1000, 1000]</p>
</td>
</tr>
<tr><td><code>mode</code> <B>[Required]</B><br/>
<a href="#kubeproxy-config-k8s-io-v1alpha1-ProxyMode"><code>ProxyMode</code></a>
</td>
<td>
   <p>mode specifies which proxy mode to use.</p>
</td>
</tr>
<tr><td><code>portRange</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>portRange is the range of host ports (beginPort-endPort, inclusive) that may be consumed
in order to proxy service traffic. If unspecified (0-0) then ports will be randomly chosen.</p>
</td>
</tr>
<tr><td><code>udpIdleTimeout</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>udpIdleTimeout is how long an idle UDP connection will be kept open (e.g. '250ms', '2s').
Must be greater than 0. Only applicable for proxyMode=userspace.</p>
</td>
</tr>
<tr><td><code>conntrack</code> <B>[Required]</B><br/>
<a href="#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConntrackConfiguration"><code>KubeProxyConntrackConfiguration</code></a>
</td>
<td>
   <p>conntrack contains conntrack-related configuration options.</p>
</td>
</tr>
<tr><td><code>configSyncPeriod</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>configSyncPeriod is how often configuration from the apiserver is refreshed. Must be greater
than 0.</p>
</td>
</tr>
<tr><td><code>nodePortAddresses</code> <B>[Required]</B><br/>
<code>[]string</code>
</td>
<td>
   <p>nodePortAddresses is the --nodeport-addresses value for kube-proxy process. Values must be valid
IP blocks. These values are as a parameter to select the interfaces where nodeport works.
In case someone would like to expose a service on localhost for local visit and some other interfaces for
particular purpose, a list of IP blocks would do that.
If set it to &quot;127.0.0.0/8&quot;, kube-proxy will only select the loopback interface for NodePort.
If set it to a non-zero IP block, kube-proxy will filter that down to just the IPs that applied to the node.
An empty string slice is meant to select all network interfaces.</p>
</td>
</tr>
<tr><td><code>winkernel</code> <B>[Required]</B><br/>
<a href="#kubeproxy-config-k8s-io-v1alpha1-KubeProxyWinkernelConfiguration"><code>KubeProxyWinkernelConfiguration</code></a>
</td>
<td>
   <p>winkernel contains winkernel-related configuration options.</p>
</td>
</tr>
<tr><td><code>showHiddenMetricsForVersion</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>ShowHiddenMetricsForVersion is the version for which you want to show hidden metrics.</p>
</td>
</tr>
<tr><td><code>detectLocalMode</code> <B>[Required]</B><br/>
<a href="#kubeproxy-config-k8s-io-v1alpha1-LocalMode"><code>LocalMode</code></a>
</td>
<td>
   <p>DetectLocalMode determines mode to use for detecting local traffic, defaults to LocalModeClusterCIDR</p>
</td>
</tr>
</tbody>
</table>

## `KubeProxyConntrackConfiguration`     {#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConntrackConfiguration}
    

**Appears in:**

- [KubeProxyConfiguration](#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConfiguration)


<p>KubeProxyConntrackConfiguration contains conntrack settings for
the Kubernetes proxy server.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
  
<tr><td><code>maxPerCore</code> <B>[Required]</B><br/>
<code>int32</code>
</td>
<td>
   <p>maxPerCore is the maximum number of NAT connections to track
per CPU core (0 to leave the limit as-is and ignore min).</p>
</td>
</tr>
<tr><td><code>min</code> <B>[Required]</B><br/>
<code>int32</code>
</td>
<td>
   <p>min is the minimum value of connect-tracking records to allocate,
regardless of conntrackMaxPerCore (set maxPerCore=0 to leave the limit as-is).</p>
</td>
</tr>
<tr><td><code>tcpEstablishedTimeout</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>tcpEstablishedTimeout is how long an idle TCP connection will be kept open
(e.g. '2s').  Must be greater than 0 to set.</p>
</td>
</tr>
<tr><td><code>tcpCloseWaitTimeout</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>tcpCloseWaitTimeout is how long an idle conntrack entry
in CLOSE_WAIT state will remain in the conntrack
table. (e.g. '60s'). Must be greater than 0 to set.</p>
</td>
</tr>
</tbody>
</table>

## `KubeProxyIPTablesConfiguration`     {#kubeproxy-config-k8s-io-v1alpha1-KubeProxyIPTablesConfiguration}
    

**Appears in:**

- [KubeProxyConfiguration](#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConfiguration)


<p>KubeProxyIPTablesConfiguration contains iptables-related configuration
details for the Kubernetes proxy server.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
  
<tr><td><code>masqueradeBit</code> <B>[Required]</B><br/>
<code>int32</code>
</td>
<td>
   <p>masqueradeBit is the bit of the iptables fwmark space to use for SNAT if using
the pure iptables proxy mode. Values must be within the range [0, 31].</p>
</td>
</tr>
<tr><td><code>masqueradeAll</code> <B>[Required]</B><br/>
<code>bool</code>
</td>
<td>
   <p>masqueradeAll tells kube-proxy to SNAT everything if using the pure iptables proxy mode.</p>
</td>
</tr>
<tr><td><code>syncPeriod</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>syncPeriod is the period that iptables rules are refreshed (e.g. '5s', '1m',
'2h22m').  Must be greater than 0.</p>
</td>
</tr>
<tr><td><code>minSyncPeriod</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>minSyncPeriod is the minimum period that iptables rules are refreshed (e.g. '5s', '1m',
'2h22m').</p>
</td>
</tr>
</tbody>
</table>

## `KubeProxyIPVSConfiguration`     {#kubeproxy-config-k8s-io-v1alpha1-KubeProxyIPVSConfiguration}
    

**Appears in:**

- [KubeProxyConfiguration](#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConfiguration)


<p>KubeProxyIPVSConfiguration contains ipvs-related configuration
details for the Kubernetes proxy server.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
  
<tr><td><code>syncPeriod</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>syncPeriod is the period that ipvs rules are refreshed (e.g. '5s', '1m',
'2h22m').  Must be greater than 0.</p>
</td>
</tr>
<tr><td><code>minSyncPeriod</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>minSyncPeriod is the minimum period that ipvs rules are refreshed (e.g. '5s', '1m',
'2h22m').</p>
</td>
</tr>
<tr><td><code>scheduler</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>ipvs scheduler</p>
</td>
</tr>
<tr><td><code>excludeCIDRs</code> <B>[Required]</B><br/>
<code>[]string</code>
</td>
<td>
   <p>excludeCIDRs is a list of CIDR's which the ipvs proxier should not touch
when cleaning up ipvs services.</p>
</td>
</tr>
<tr><td><code>strictARP</code> <B>[Required]</B><br/>
<code>bool</code>
</td>
<td>
   <p>strict ARP configure arp_ignore and arp_announce to avoid answering ARP queries
from kube-ipvs0 interface</p>
</td>
</tr>
<tr><td><code>tcpTimeout</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>tcpTimeout is the timeout value used for idle IPVS TCP sessions.
The default value is 0, which preserves the current timeout value on the system.</p>
</td>
</tr>
<tr><td><code>tcpFinTimeout</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>tcpFinTimeout is the timeout value used for IPVS TCP sessions after receiving a FIN.
The default value is 0, which preserves the current timeout value on the system.</p>
</td>
</tr>
<tr><td><code>udpTimeout</code> <B>[Required]</B><br/>
<a href="https://pkg.go.dev/k8s.io/apimachinery/pkg/apis/meta/v1#Duration"><code>meta/v1.Duration</code></a>
</td>
<td>
   <p>udpTimeout is the timeout value used for IPVS UDP packets.
The default value is 0, which preserves the current timeout value on the system.</p>
</td>
</tr>
</tbody>
</table>

## `KubeProxyWinkernelConfiguration`     {#kubeproxy-config-k8s-io-v1alpha1-KubeProxyWinkernelConfiguration}
    

**Appears in:**

- [KubeProxyConfiguration](#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConfiguration)


<p>KubeProxyWinkernelConfiguration contains Windows/HNS settings for
the Kubernetes proxy server.</p>


<table class="table">
<thead><tr><th width="30%">Field</th><th>Description</th></tr></thead>
<tbody>
    
  
<tr><td><code>networkName</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>networkName is the name of the network kube-proxy will use
to create endpoints and policies</p>
</td>
</tr>
<tr><td><code>sourceVip</code> <B>[Required]</B><br/>
<code>string</code>
</td>
<td>
   <p>sourceVip is the IP address of the source VIP endoint used for
NAT when loadbalancing</p>
</td>
</tr>
<tr><td><code>enableDSR</code> <B>[Required]</B><br/>
<code>bool</code>
</td>
<td>
   <p>enableDSR tells kube-proxy whether HNS policies should be created
with DSR</p>
</td>
</tr>
</tbody>
</table>

## `LocalMode`     {#kubeproxy-config-k8s-io-v1alpha1-LocalMode}
    
(Alias of `string`)

**Appears in:**

- [KubeProxyConfiguration](#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConfiguration)


<p>LocalMode represents modes to detect local traffic from the node</p>




## `ProxyMode`     {#kubeproxy-config-k8s-io-v1alpha1-ProxyMode}
    
(Alias of `string`)

**Appears in:**

- [KubeProxyConfiguration](#kubeproxy-config-k8s-io-v1alpha1-KubeProxyConfiguration)


<p>ProxyMode represents modes used by the Kubernetes proxy server.</p>
<p>Currently, three modes of proxy are available in Linux platform: 'userspace' (older, going to be EOL), 'iptables'
(newer, faster), 'ipvs'(newest, better in performance and scalability).</p>
<p>Two modes of proxy are available in Windows platform: 'userspace'(older, stable) and 'kernelspace' (newer, faster).</p>
<p>In Linux platform, if proxy mode is blank, use the best-available proxy (currently iptables, but may change in the
future). If the iptables proxy is selected, regardless of how, but the system's kernel or iptables versions are
insufficient, this always falls back to the userspace proxy. IPVS mode will be enabled when proxy mode is set to 'ipvs',
and the fall back path is firstly iptables and then userspace.</p>
<p>In Windows platform, if proxy mode is blank, use the best-available proxy (currently userspace, but may change in the
future). If winkernel proxy is selected, regardless of how, but the Windows kernel can't support this mode of proxy,
this always falls back to the userspace proxy.</p>



  
