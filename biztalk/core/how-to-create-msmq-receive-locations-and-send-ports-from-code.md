---
title: 创建 MSMQ 接收位置和发送端口从代码 |Microsoft Docs
description: 以编程方式创建 MSMQ 接收位置和 BizTalk Server 中的发送端口
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
ms.openlocfilehash: e79cde5da2347a51894ca402740a680e9bd14d1d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385494"
---
# <a name="create-msmq-receive-locations-and-send-ports-programmatically"></a><span data-ttu-id="9da33-103">以编程方式创建 MSMQ 接收位置和发送端口</span><span class="sxs-lookup"><span data-stu-id="9da33-103">Create MSMQ Receive Locations and Send Ports programmatically</span></span>
<span data-ttu-id="9da33-104">本主题说明如何使用 WMI 创建端口或 MSMQ 适配器的位置。</span><span class="sxs-lookup"><span data-stu-id="9da33-104">This topic explains how to use WMI to create a port or location for the MSMQ adapter.</span></span>  
  
 <span data-ttu-id="9da33-105">有关详细信息，请参阅**使用一个日期时间计划配置使用 WMI 创建接收位置** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="9da33-105">For more information, see **Creating a Receive Location with a Datetime Schedule Configuration Using WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="setting-property-values"></a><span data-ttu-id="9da33-106">设置属性值</span><span class="sxs-lookup"><span data-stu-id="9da33-106">Setting Property Values</span></span>  
 <span data-ttu-id="9da33-107">创建端口或位置的过程始终是相同的：</span><span class="sxs-lookup"><span data-stu-id="9da33-107">The process of creating a port or location is always the same:</span></span>  
  
1. <span data-ttu-id="9da33-108">创建正确类型的对象。</span><span class="sxs-lookup"><span data-stu-id="9da33-108">Create an object of the right type.</span></span>  
  
2. <span data-ttu-id="9da33-109">在对象上设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="9da33-109">Set the value of properties on the object.</span></span>  
  
3. <span data-ttu-id="9da33-110">将对象值提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="9da33-110">Commit the object values to the database.</span></span>  
  
   <span data-ttu-id="9da33-111">所有适配器都具有某些属性，如**主机名**、 共同点。</span><span class="sxs-lookup"><span data-stu-id="9da33-111">All adapters have certain properties, such as **HostName**, in common.</span></span> <span data-ttu-id="9da33-112">通过直接将它们分配给该对象设置这些通用属性。</span><span class="sxs-lookup"><span data-stu-id="9da33-112">You set these common properties by directly assigning them to the object.</span></span> <span data-ttu-id="9da33-113">下面的 C# 代码显示了典型的用例：</span><span class="sxs-lookup"><span data-stu-id="9da33-113">The following C# code shows a typical case:</span></span>  
  
```  
objReceiveLocation["HostName"] = "BizTalkServerApplication";  
```  
  
 <span data-ttu-id="9da33-114">将值分配到不是所有适配器都共享的属性。</span><span class="sxs-lookup"><span data-stu-id="9da33-114">You assign values to properties that not all adapters share.</span></span> <span data-ttu-id="9da33-115">在字符串中创建 XML 文档并将该字符串分配给 CustomCfg 属性。</span><span class="sxs-lookup"><span data-stu-id="9da33-115">You create an XML document in a string and assign that string to the CustomCfg property.</span></span> <span data-ttu-id="9da33-116">下面的 C# 代码演示文件适配器的典型事例：</span><span class="sxs-lookup"><span data-stu-id="9da33-116">The following C# code shows a typical case for a FILE adapter:</span></span>  
  
```  
objReceiveLocation["CustomCfg"] =   
        @"<CustomProps>"  
        + @"<BatchSize>20</BatchSize>"  
        + @"<FileMask>*.xml</FileMask>"  
        + @"<FileNetFailRetryCount>5</FileNetFailRetryCount>"  
        + @"<FileNetFailRetryInt>5</FileNetFailRetryInt>"  
        + @"</CustomProps>";  
```  
  
 <span data-ttu-id="9da33-117">CustomProps 元素中的标记的名称是该适配器将使用的属性的内部名称。</span><span class="sxs-lookup"><span data-stu-id="9da33-117">The names of the tags in the CustomProps element are the internal names that the adapter uses for the properties.</span></span>  
  
 <span data-ttu-id="9da33-118">MSMQ 适配器具有单个标记 AdapterConfig CustomProps 标记内。</span><span class="sxs-lookup"><span data-stu-id="9da33-118">The MSMQ adapter has a single tag, AdapterConfig, inside the CustomProps tag.</span></span> <span data-ttu-id="9da33-119">AdapterConfig 标记包含用 Config 标记括起来的自定义属性值的 XML 标记的字符串。</span><span class="sxs-lookup"><span data-stu-id="9da33-119">The AdapterConfig tag contains a string of XML tags for the custom property values enclosed in a Config tag.</span></span> <span data-ttu-id="9da33-120">但是，编码的标记:"&lt;"替换"\<"和"&gt;"替换"\>"。</span><span class="sxs-lookup"><span data-stu-id="9da33-120">However, the tags are encoded: "&lt;" replaces "\<" and "&gt;" replaces "\>".</span></span> <span data-ttu-id="9da33-121">例如，MSMQ 属性的适配器子集 XML 可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="9da33-121">For example, the XML for a subset of the adapter for MSMQ properties might appear as follows:</span></span>  
  
```  
<Config>  
    <batchSize>40</batchSize>  
</Config>  
```  
  
 <span data-ttu-id="9da33-122">请注意， **vt**未使用属性。</span><span class="sxs-lookup"><span data-stu-id="9da33-122">Notice that the **vt** attribute is not used.</span></span> <span data-ttu-id="9da33-123">将字符串分配给**CustomCfg**属性编码后显示，如下所示：</span><span class="sxs-lookup"><span data-stu-id="9da33-123">The string assigned to the **CustomCfg** property appears as follows after encoding:</span></span>  
  
```  
<CustomProps><AdapterConfig vt="8"><Config><batchSize>40</batchSize></Config></AdapterConfig></CustomProps>  
```  
  
## <a name="custom-property-names"></a><span data-ttu-id="9da33-124">自定义属性名称</span><span class="sxs-lookup"><span data-stu-id="9da33-124">Custom Property Names</span></span>  
 <span data-ttu-id="9da33-125">下表描述了 MSMQ 适配器的内部名称**发送**自定义属性。</span><span class="sxs-lookup"><span data-stu-id="9da33-125">The following table describes the internal names of the MSMQ adapter **Send** custom properties.</span></span>  
  
|<span data-ttu-id="9da33-126">**发送自定义属性名称**</span><span class="sxs-lookup"><span data-stu-id="9da33-126">**Send custom property name**</span></span>|<span data-ttu-id="9da33-127">**显示名称**</span><span class="sxs-lookup"><span data-stu-id="9da33-127">**Display name**</span></span>|  
|-----------------------------------|----------------------|  
|<span data-ttu-id="9da33-128">acknowledgeType</span><span class="sxs-lookup"><span data-stu-id="9da33-128">acknowledgeType</span></span>|<span data-ttu-id="9da33-129">确认类型</span><span class="sxs-lookup"><span data-stu-id="9da33-129">Acknowledgement Type</span></span>|  
|<span data-ttu-id="9da33-130">administrationQueue</span><span class="sxs-lookup"><span data-stu-id="9da33-130">administrationQueue</span></span>|<span data-ttu-id="9da33-131">管理队列</span><span class="sxs-lookup"><span data-stu-id="9da33-131">Administration Queue</span></span>|  
|<span data-ttu-id="9da33-132">证书 (certificate)</span><span class="sxs-lookup"><span data-stu-id="9da33-132">certificate</span></span>|<span data-ttu-id="9da33-133">证书指纹</span><span class="sxs-lookup"><span data-stu-id="9da33-133">Certificate Thumbprint</span></span>|  
|<span data-ttu-id="9da33-134">encryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="9da33-134">encryptionAlgorithm</span></span>|<span data-ttu-id="9da33-135">加密算法</span><span class="sxs-lookup"><span data-stu-id="9da33-135">Encryption Algorithm</span></span>|  
|<span data-ttu-id="9da33-136">maximumMessageSize</span><span class="sxs-lookup"><span data-stu-id="9da33-136">maximumMessageSize</span></span>|<span data-ttu-id="9da33-137">最大消息大小 （以 kb 为单位）</span><span class="sxs-lookup"><span data-stu-id="9da33-137">Maximum Message Size (in KB)</span></span>|  
|<span data-ttu-id="9da33-138">password</span><span class="sxs-lookup"><span data-stu-id="9da33-138">password</span></span>|<span data-ttu-id="9da33-139">Password</span><span class="sxs-lookup"><span data-stu-id="9da33-139">Password</span></span>|  
|<span data-ttu-id="9da33-140">priority</span><span class="sxs-lookup"><span data-stu-id="9da33-140">priority</span></span>|<span data-ttu-id="9da33-141">消息优先级</span><span class="sxs-lookup"><span data-stu-id="9da33-141">Message Priority</span></span>|  
|<span data-ttu-id="9da33-142">queue</span><span class="sxs-lookup"><span data-stu-id="9da33-142">queue</span></span>|<span data-ttu-id="9da33-143">目标队列</span><span class="sxs-lookup"><span data-stu-id="9da33-143">Destination Queue</span></span>|  
|<span data-ttu-id="9da33-144">可恢复</span><span class="sxs-lookup"><span data-stu-id="9da33-144">recoverable</span></span>|<span data-ttu-id="9da33-145">可恢复</span><span class="sxs-lookup"><span data-stu-id="9da33-145">Recoverable</span></span>|  
|<span data-ttu-id="9da33-146">segmentationSupport</span><span class="sxs-lookup"><span data-stu-id="9da33-146">segmentationSupport</span></span>|<span data-ttu-id="9da33-147">支持分段</span><span class="sxs-lookup"><span data-stu-id="9da33-147">Support Segmentation</span></span>|  
|<span data-ttu-id="9da33-148">sendBatchSize</span><span class="sxs-lookup"><span data-stu-id="9da33-148">sendBatchSize</span></span>|<span data-ttu-id="9da33-149">批大小</span><span class="sxs-lookup"><span data-stu-id="9da33-149">Batch Size</span></span>|  
|<span data-ttu-id="9da33-150">sendQueueName</span><span class="sxs-lookup"><span data-stu-id="9da33-150">sendQueueName</span></span>|<span data-ttu-id="9da33-151">目标队列</span><span class="sxs-lookup"><span data-stu-id="9da33-151">Destination Queue</span></span>|  
|<span data-ttu-id="9da33-152">timeOut</span><span class="sxs-lookup"><span data-stu-id="9da33-152">timeOut</span></span>|<span data-ttu-id="9da33-153">超时</span><span class="sxs-lookup"><span data-stu-id="9da33-153">Timeout</span></span>|  
|<span data-ttu-id="9da33-154">timeOutUnits</span><span class="sxs-lookup"><span data-stu-id="9da33-154">timeOutUnits</span></span>|<span data-ttu-id="9da33-155">超时单位</span><span class="sxs-lookup"><span data-stu-id="9da33-155">Timeout Unit</span></span>|  
|<span data-ttu-id="9da33-156">事务</span><span class="sxs-lookup"><span data-stu-id="9da33-156">transactional</span></span>|<span data-ttu-id="9da33-157">事务性</span><span class="sxs-lookup"><span data-stu-id="9da33-157">Transactional</span></span>|  
|<span data-ttu-id="9da33-158">useAuthentication</span><span class="sxs-lookup"><span data-stu-id="9da33-158">useAuthentication</span></span>|<span data-ttu-id="9da33-159">使用身份验证</span><span class="sxs-lookup"><span data-stu-id="9da33-159">Use Authentication</span></span>|  
|<span data-ttu-id="9da33-160">useDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="9da33-160">useDeadLetterQueue</span></span>|<span data-ttu-id="9da33-161">使用死信队列</span><span class="sxs-lookup"><span data-stu-id="9da33-161">Use Dead Letter Queue</span></span>|  
|<span data-ttu-id="9da33-162">useJournalQueue</span><span class="sxs-lookup"><span data-stu-id="9da33-162">useJournalQueue</span></span>|<span data-ttu-id="9da33-163">使用日志队列</span><span class="sxs-lookup"><span data-stu-id="9da33-163">Use Journal Queue</span></span>|  
|<span data-ttu-id="9da33-164">userName</span><span class="sxs-lookup"><span data-stu-id="9da33-164">userName</span></span>|<span data-ttu-id="9da33-165">用户名</span><span class="sxs-lookup"><span data-stu-id="9da33-165">User Name</span></span>|  
  
 <span data-ttu-id="9da33-166">下表描述了 MSMQ 适配器的内部名称**接收**自定义属性。</span><span class="sxs-lookup"><span data-stu-id="9da33-166">The following table describes the internal names of the MSMQ adapter **Receive** custom properties.</span></span>  
  
|<span data-ttu-id="9da33-167">**接收自定义属性名称**</span><span class="sxs-lookup"><span data-stu-id="9da33-167">**Receive custom property name**</span></span>|<span data-ttu-id="9da33-168">**显示名称**</span><span class="sxs-lookup"><span data-stu-id="9da33-168">**Display name**</span></span>|  
|--------------------------------------|----------------------|  
|<span data-ttu-id="9da33-169">batchSize</span><span class="sxs-lookup"><span data-stu-id="9da33-169">batchSize</span></span>|<span data-ttu-id="9da33-170">批大小</span><span class="sxs-lookup"><span data-stu-id="9da33-170">Batch Size</span></span>|  
|<span data-ttu-id="9da33-171">Password</span><span class="sxs-lookup"><span data-stu-id="9da33-171">Password</span></span>|<span data-ttu-id="9da33-172">Password</span><span class="sxs-lookup"><span data-stu-id="9da33-172">Password</span></span>|  
|<span data-ttu-id="9da33-173">队列</span><span class="sxs-lookup"><span data-stu-id="9da33-173">Queue</span></span>|<span data-ttu-id="9da33-174">队列</span><span class="sxs-lookup"><span data-stu-id="9da33-174">Queue</span></span>|  
|<span data-ttu-id="9da33-175">serialProcessing</span><span class="sxs-lookup"><span data-stu-id="9da33-175">serialProcessing</span></span>|<span data-ttu-id="9da33-176">串行处理</span><span class="sxs-lookup"><span data-stu-id="9da33-176">Serial Processing</span></span>|  
|<span data-ttu-id="9da33-177">事务性</span><span class="sxs-lookup"><span data-stu-id="9da33-177">Transactional</span></span>|<span data-ttu-id="9da33-178">事务性</span><span class="sxs-lookup"><span data-stu-id="9da33-178">Transactional</span></span>|  
|<span data-ttu-id="9da33-179">userName</span><span class="sxs-lookup"><span data-stu-id="9da33-179">userName</span></span>|<span data-ttu-id="9da33-180">用户名</span><span class="sxs-lookup"><span data-stu-id="9da33-180">User Name</span></span>|  
  
## <a name="sample-code"></a><span data-ttu-id="9da33-181">示例代码</span><span class="sxs-lookup"><span data-stu-id="9da33-181">Sample Code</span></span>  
 <span data-ttu-id="9da33-182">下面的 C# 程序创建一个 MSMQ 适配器的接收位置。</span><span class="sxs-lookup"><span data-stu-id="9da33-182">The following C# program creates a single receive location for the MSMQ adapter.</span></span> <span data-ttu-id="9da33-183">它假定接收端口 ReceivePort1 存在，并且使用一个帮助程序函数进行编码和格式化的自定义属性。</span><span class="sxs-lookup"><span data-stu-id="9da33-183">It assumes that the receive port, ReceivePort1, exists and uses a helper function to encode and format the custom properties.</span></span>  
  
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