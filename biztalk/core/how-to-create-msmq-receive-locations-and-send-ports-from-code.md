---
title: 创建 MSMQ 代码从接收位置和发送端口 |Microsoft 文档
description: 以编程方式创建 MSMQ 接收位置和在 BizTalk Server 发送端口
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ebb4119-deeb-4287-aa65-7597ff0cc435
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5f00a0bfe14eeb7d4205973b3fef96e23026616
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971667"
---
# <a name="create-msmq-receive-locations-and-send-ports-programmatically"></a>以编程方式创建 MSMQ 接收位置和发送端口
本主题说明了如何使用 WMI 为 MSMQ 适配器创建端口或位置。  
  
 有关详细信息，请参阅**使用 Datetime 计划配置使用 WMI 创建接收位置** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="setting-property-values"></a>设置属性值  
 创建端口或位置的过程始终相同：  
  
1.  创建正确类型的对象。  
  
2.  对该对象设置属性值。  
  
3.  将对象值提交给数据库。  
  
 所有适配器都具有某些属性，如**主机名**、 共同点。 可通过直接将这些通用属性分配给对象来设置这些属性。 下面的 C# 代码显示的是一种典型的情况：  
  
```  
objReceiveLocation["HostName"] = "BizTalkServerApplication";  
```  
  
 对不是所有适配器都共享的属性赋值。 以字符串格式创建一个 XML 文档，然后将该字符串分配给 CustomCfg 属性。 下面的 C# 代码显示了一种针对 FILE 适配器的典型情况：  
  
```  
objReceiveLocation["CustomCfg"] =   
        @"<CustomProps>"  
        + @"<BatchSize>20</BatchSize>"  
        + @"<FileMask>*.xml</FileMask>"  
        + @"<FileNetFailRetryCount>5</FileNetFailRetryCount>"  
        + @"<FileNetFailRetryInt>5</FileNetFailRetryInt>"  
        + @"</CustomProps>";  
```  
  
 CustomProps 元素中的标记的名称是该适配器用于这些属性的内部名称。  
  
 MSMQ 适配器在 CustomProps 标记的内部具有单个标记 AdapterConfig。 AdapterConfig 标记包含用 Config 标记括起来的自定义属性值的 XML 标记字符串。 但是，编码标记:"&lt;"替换"\<"和"&gt;"替换"\>"。 例如， MSMQ 属性的适配器子集 XML 可能会如下所示：  
  
```  
<Config>  
    <batchSize>40</batchSize>  
</Config>  
```  
  
 请注意， **vt**不使用属性。 分配给字符串**CustomCfg**属性编码后出现，如下所示：  
  
```  
<CustomProps><AdapterConfig vt="8"><Config><batchSize>40</batchSize></Config></AdapterConfig></CustomProps>  
```  
  
## <a name="custom-property-names"></a>自定义属性名称  
 下表描述了 MSMQ 适配器的内部名称**发送**自定义属性。  
  
|**发送自定义属性名称**|**显示名称**|  
|-----------------------------------|----------------------|  
|acknowledgeType|确认类型|  
|administrationQueue|管理队列|  
|证书 (certificate)|证书指纹|  
|encryptionAlgorithm|加密算法|  
|maximumMessageSize|最大消息大小（以 KB 为单位）|  
|password|密码|  
|priority|消息优先级|  
|queue|目标队列|  
|recoverable|Recoverable|  
|segmentationSupport|支持分段|  
|sendBatchSize|批大小|  
|sendQueueName|目标队列|  
|timeOut|超时|  
|timeOutUnits|超时单元|  
|transactional|事务性|  
|useAuthentication|使用身份验证|  
|useDeadLetterQueue|使用死信队列|  
|useJournalQueue|使用日记队列|  
|userName|用户名|  
  
 下表描述了 MSMQ 适配器的内部名称**接收**自定义属性。  
  
|**接收自定义属性名称**|**显示名称**|  
|--------------------------------------|----------------------|  
|batchSize|批大小|  
|密码|密码|  
|队列|队列|  
|serialProcessing|串行处理|  
|事务性|事务性|  
|userName|用户名|  
  
## <a name="sample-code"></a>示例代码  
 下面的 C# 程序为 MSMQ 适配器创建了单个接收位置。 该程序假定接收端口 ReceivePort1 存在，且使用 Helper 函数对自定义属性进行编码和格式化。  
  
```  
using System;  
using System.Management;  
using System.Text;  
  
namespace CreateReceive  
{  
    ///   
    /// Program to create a receive location.  
    ///   
    class CreateReceive  
    {  
        /// The main entry point for the application.  
  
        [STAThread]  
        static void Main()  
        {  
            // Custom properties & values  
            string cfg =   
                    @"<queue>FORMATNAME:DIRECT=OS:MYMACHINE02\PRIVATE$\QUEUE2</queue>"  
                    + @"<batchSize>40</batchSize>"  
                    + @"<transactional>true</transactional>"  
                    + @"<serialProcessing>false</serialProcessing>";  
  
            CreateReceiveLocation (  
                    "Code Created Location",  
                    "ReceivePort1",  
                    "MSMQ",  
                    "BizTalkServerApplication",  
                    EncodeCustomProps(cfg),  // Encode the custom props  
                    "Microsoft.BizTalk.DefaultPipelines.PassThruReceive,"   
                            + " Microsoft.BizTalk.DefaultPipelines,"   
                            + " Version=3.0.1.0, Culture=neutral,"   
                            + " PublicKeyToken=31bf3856ad364e35",  
                    @"FORMATNAME:DIRECT=OS:MYMACHINE\PRIVATE$\QUEUE2"  
                );  
  
        }  
  
        static string EncodeCustomProps (string cp) {  
  
            // Enclose the properties and values in a Config> tag.  
            StringBuilder tmp = new StringBuilder( @"<Config>" + cp + @"</Config>");  
  
            // Encode the string  
            tmp = tmp.Replace("<","<");  
            tmp = tmp.Replace(">",">");  
  
            return (  
                // Enclose the encoded string with necessary tags  
                "<CustomProps><AdapterConfig vt=\"8\">"  
                + tmp.ToString()   
                + "</AdapterConfig></CustomProps>");  
  
        }  
  
        static void CreateReceiveLocation (  
            string name,            // Location name  
            string port,            // Receive port, already exists  
            string adapterName,     // The transport type  
            string hostName,        // BTS host  
            string customCfg,       // Encoded custom properties  
            string pipeline,        // Full specification of pipeline  
            string inboundTransport)// Inbound transport url  
        {  
            try   
            {  
                // Create options to store options in management object  
                PutOptions options = new PutOptions();  
                options.Type = PutType.CreateOnly;  
  
                // Create a management object  
                // Get the class  
                ManagementClass objReceiveLocationClass =   
                           new ManagementClass(  
                               "root\\MicrosoftBizTalkServer",   
                               "MSBTS_ReceiveLocation",   
                               null);  
                // Create an instance of the member of the class  
                ManagementObject objReceiveLocation =  
                          objReceiveLocationClass.CreateInstance();  
  
                // Fill in the properties  
                objReceiveLocation["Name"] = name;  
                objReceiveLocation["ReceivePortName"] = port;  
                objReceiveLocation["AdapterName"] = adapterName;  
                objReceiveLocation["HostName"] = hostName;  
                objReceiveLocation["PipelineName"] = pipeline;  
                objReceiveLocation["CustomCfg"] = customCfg;  
                objReceiveLocation["IsDisabled"] = true;  
                objReceiveLocation["InBoundTransportURL"] = inboundTransport;  
  
                // Put the options -- creates the receive location  
                objReceiveLocation.Put(options);  
            }  
            catch (Exception excep)  
            {  
                System.Console.WriteLine("Create Receive Location ({0}) failed - {1}",  
                                                name, excep.Message);  
            }  
        }  
    }  
}  
```