# 通过OpenAPI Explorer创建VPC类型实例时指定IP {#task_rz1_xqj_mfb .task}

使用APIexplorer创建VPC类型负载均衡实例时，支持在负载均衡实例所属交换机支持的网段中，指定其中一个地址作为负载均衡实例的私网IP地址。

1.  登录[OpenAPI Explorer控制台](https://api.aliyun.com/)。 
2.  搜索负载均衡产品的CreateLoadBalancer接口。 
3.  设置创建负载均衡实例的参数。 此处设置部分参数作为示例，详细参数说明参见[../../../../dita-oss-bucket/SP\_23/DNSLB11870158/ZH-CN\_TP\_4182.md\#](../../../../intl.zh-CN/API参考/负载均衡实例/CreateLoadBalancer.md#)：
    -   RegionId：表示负载均衡实例的地域，此处设置为cn-hangzhou。
    -   VpcId：表示负载均衡实例所属VPC的ID。

        此处可登录专有网络VPC控制台，选择华东1（杭州）区域，查看VPC的ID。

    -   VSwitchId：表示负载均衡所属交换机的ID，如果需要指定负载均衡IP地址，该参数必须要设置。

        此处可在专有网络VPC控制台，单击负载均衡实例所属VPC的ID，在网络资源页面下，单击交换机的个数，查看交换机的ID。

        单击交换机ID，查看交换机的目标网段，如192.168.0.0/24。

    -   Address：指定负载均衡实例的私网IP地址，该地址必须包含在交换机的目标网段下，如192.168.0.3。
4.  单击**发送请求**。 返回结果如下：
    -   XML格式

        ```
        <?xml version="1.0" encoding="UTF-8" ?>
        	<NetworkType>vpc</NetworkType>
        	<LoadBalancerName>auto_named_slb</LoadBalancerName>
        	<Address>192.168.0.3</Address>
        	<ResourceGroupId>rg-acfmxazb4ph6aiy</ResourceGroupId>
        	<RequestId>09197EEB-7013-4F56-A5CE-A756FFE5B75D</RequestId>
        	<AddressIPVersion>ipv4</AddressIPVersion>
        	<LoadBalancerId>lb-bp1h66tp5uat84khmqc9e</LoadBalancerId>
        	<VSwitchId>vsw-bp14cagpfysr29feg5t97</VSwitchId>
        	<VpcId>vpc-bp18sth14qii3pnvodkvt</VpcId>
        ```

    -   JSON格式

        ```
        {
            "NetworkType": "vpc", 
            "LoadBalancerName": "auto_named_slb", 
            "Address": "192.168.0.3", 
            "ResourceGroupId": "rg-acfmxazb4ph6aiy", 
            "RequestId": "09197EEB-7013-4F56-A5CE-A756FFE5B75D", 
            "AddressIPVersion": "ipv4", 
            "LoadBalancerId": "lb-bp1h66tp5uat84khmqc9e", 
            "VSwitchId": "vsw-bp14cagpfysr29feg5t97", 
            "VpcId": "vpc-bp18sth14qii3pnvodkvt"
        }
        ```

5.  登录[负载均衡管理控制台](https://slb.console.aliyun.com/slb/cn-hangzhou/slbs)，选择华东1（杭州）区域，查看IP为192.168.0.3的负载均衡实例是否创建成功。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/23817/155800995813814_zh-CN.png)


