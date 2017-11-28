---
title: "创建 MSMQ 代码从接收位置和发送端口 |Microsoft 文档"
description: "以编程方式创建 MSMQ 接收位置和在 BizTalk Server 发送端口"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6ebb4119-deeb-4287-aa65-7597ff0cc435
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d362ae262c7b054bd86fda72f8aacd3b5ab1455
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-msmq-receive-locations-and-send-ports-programmatically"></a><span data-ttu-id="45078-103">以编程方式创建 MSMQ 接收位置和发送端口</span><span class="sxs-lookup"><span data-stu-id="45078-103">Create MSMQ Receive Locations and Send Ports programmatically</span></span>
<span data-ttu-id="45078-104">本主题说明了如何使用 WMI 为 MSMQ 适配器创建端口或位置。</span><span class="sxs-lookup"><span data-stu-id="45078-104">This topic explains how to use WMI to create a port or location for the MSMQ adapter.</span></span>  
  
 <span data-ttu-id="45078-105">有关详细信息，请参阅**使用 Datetime 计划配置使用 WMI 创建接收位置** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="45078-105">For more information, see **Creating a Receive Location with a Datetime Schedule Configuration Using WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="setting-property-values"></a><span data-ttu-id="45078-106">设置属性值</span><span class="sxs-lookup"><span data-stu-id="45078-106">Setting Property Values</span></span>  
 <span data-ttu-id="45078-107">创建端口或位置的过程始终相同：</span><span class="sxs-lookup"><span data-stu-id="45078-107">The process of creating a port or location is always the same:</span></span>  
  
1.  <span data-ttu-id="45078-108">创建正确类型的对象。</span><span class="sxs-lookup"><span data-stu-id="45078-108">Create an object of the right type.</span></span>  
  
2.  <span data-ttu-id="45078-109">对该对象设置属性值。</span><span class="sxs-lookup"><span data-stu-id="45078-109">Set the value of properties on the object.</span></span>  
  
3.  <span data-ttu-id="45078-110">将对象值提交给数据库。</span><span class="sxs-lookup"><span data-stu-id="45078-110">Commit the object values to the database.</span></span>  
  
 <span data-ttu-id="45078-111">所有适配器都具有某些属性，如**主机名**、 共同点。</span><span class="sxs-lookup"><span data-stu-id="45078-111">All adapters have certain properties, such as **HostName**, in common.</span></span> <span data-ttu-id="45078-112">可通过直接将这些通用属性分配给对象来设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="45078-112">You set these common properties by directly assigning them to the object.</span></span> <span data-ttu-id="45078-113">下面的 C# 代码显示的是一种典型的情况：</span><span class="sxs-lookup"><span data-stu-id="45078-113">The following C# code shows a typical case:</span></span>  
  
```  
objReceiveLocation["HostName"] = "BizTalkServerApplication";  
```  
  
 <span data-ttu-id="45078-114">对不是所有适配器都共享的属性赋值。</span><span class="sxs-lookup"><span data-stu-id="45078-114">You assign values to properties that not all adapters share.</span></span> <span data-ttu-id="45078-115">以字符串格式创建一个 XML 文档，然后将该字符串分配给 CustomCfg 属性。</span><span class="sxs-lookup"><span data-stu-id="45078-115">You create an XML document in a string and assign that string to the CustomCfg property.</span></span> <span data-ttu-id="45078-116">下面的 C# 代码显示了一种针对 FILE 适配器的典型情况：</span><span class="sxs-lookup"><span data-stu-id="45078-116">The following C# code shows a typical case for a FILE adapter:</span></span>  
  
```  
objReceiveLocation["CustomCfg"] =   
        @"<CustomProps>"  
        + @"<BatchSize>20</BatchSize>"  
        + @"<FileMask>*.xml</FileMask>"  
        + @"<FileNetFailRetryCount>5</FileNetFailRetryCount>"  
        + @"<FileNetFailRetryInt>5</FileNetFailRetryInt>"  
        + @"</CustomProps>";  
```  
  
 <span data-ttu-id="45078-117">CustomProps 元素中的标记的名称是该适配器用于这些属性的内部名称。</span><span class="sxs-lookup"><span data-stu-id="45078-117">The names of the tags in the CustomProps element are the internal names that the adapter uses for the properties.</span></span>  
  
 <span data-ttu-id="45078-118">MSMQ 适配器在 CustomProps 标记的内部具有单个标记 AdapterConfig。</span><span class="sxs-lookup"><span data-stu-id="45078-118">The MSMQ adapter has a single tag, AdapterConfig, inside the CustomProps tag.</span></span> <span data-ttu-id="45078-119">AdapterConfig 标记包含用 Config 标记括起来的自定义属性值的 XML 标记字符串。</span><span class="sxs-lookup"><span data-stu-id="45078-119">The AdapterConfig tag contains a string of XML tags for the custom property values enclosed in a Config tag.</span></span> <span data-ttu-id="45078-120">但是，编码标记:"&lt;"替换"\<"和"&gt;"替换">"。</span><span class="sxs-lookup"><span data-stu-id="45078-120">However, the tags are encoded: "&lt;" replaces "\<" and "&gt;" replaces ">".</span></span> <span data-ttu-id="45078-121">例如， MSMQ 属性的适配器子集 XML 可能会如下所示：</span><span class="sxs-lookup"><span data-stu-id="45078-121">For example, the XML for a subset of the adapter for MSMQ properties might appear as follows:</span></span>  
  
```  
<Config>  
    <batchSize>40</batchSize>  
</Config>  
```  
  
 <span data-ttu-id="45078-122">请注意， **vt**不使用属性。</span><span class="sxs-lookup"><span data-stu-id="45078-122">Notice that the **vt** attribute is not used.</span></span> <span data-ttu-id="45078-123">分配给字符串**CustomCfg**属性编码后出现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="45078-123">The string assigned to the **CustomCfg** property appears as follows after encoding:</span></span>  
  
```  
<CustomProps><AdapterConfig vt="8"><Config><batchSize>40</batchSize></Config></AdapterConfig></CustomProps>  
```  
  
## <a name="custom-property-names"></a><span data-ttu-id="45078-124">自定义属性名称</span><span class="sxs-lookup"><span data-stu-id="45078-124">Custom Property Names</span></span>  
 <span data-ttu-id="45078-125">下表描述了 MSMQ 适配器的内部名称**发送**自定义属性。</span><span class="sxs-lookup"><span data-stu-id="45078-125">The following table describes the internal names of the MSMQ adapter **Send** custom properties.</span></span>  
  
|<span data-ttu-id="45078-126">**发送自定义属性名称**</span><span class="sxs-lookup"><span data-stu-id="45078-126">**Send custom property name**</span></span>|<span data-ttu-id="45078-127">**显示名称**</span><span class="sxs-lookup"><span data-stu-id="45078-127">**Display name**</span></span>|  
|-----------------------------------|----------------------|  
|<span data-ttu-id="45078-128">acknowledgeType</span><span class="sxs-lookup"><span data-stu-id="45078-128">acknowledgeType</span></span>|<span data-ttu-id="45078-129">确认类型</span><span class="sxs-lookup"><span data-stu-id="45078-129">Acknowledgement Type</span></span>|  
|<span data-ttu-id="45078-130">administrationQueue</span><span class="sxs-lookup"><span data-stu-id="45078-130">administrationQueue</span></span>|<span data-ttu-id="45078-131">管理队列</span><span class="sxs-lookup"><span data-stu-id="45078-131">Administration Queue</span></span>|  
|<span data-ttu-id="45078-132">证书 (certificate)</span><span class="sxs-lookup"><span data-stu-id="45078-132">certificate</span></span>|<span data-ttu-id="45078-133">证书指纹</span><span class="sxs-lookup"><span data-stu-id="45078-133">Certificate Thumbprint</span></span>|  
|<span data-ttu-id="45078-134">encryptionAlgorithm</span><span class="sxs-lookup"><span data-stu-id="45078-134">encryptionAlgorithm</span></span>|<span data-ttu-id="45078-135">加密算法</span><span class="sxs-lookup"><span data-stu-id="45078-135">Encryption Algorithm</span></span>|  
|<span data-ttu-id="45078-136">maximumMessageSize</span><span class="sxs-lookup"><span data-stu-id="45078-136">maximumMessageSize</span></span>|<span data-ttu-id="45078-137">最大消息大小（以 KB 为单位）</span><span class="sxs-lookup"><span data-stu-id="45078-137">Maximum Message Size (in KB)</span></span>|  
|<span data-ttu-id="45078-138">password</span><span class="sxs-lookup"><span data-stu-id="45078-138">password</span></span>|<span data-ttu-id="45078-139">密码</span><span class="sxs-lookup"><span data-stu-id="45078-139">Password</span></span>|  
|<span data-ttu-id="45078-140">priority</span><span class="sxs-lookup"><span data-stu-id="45078-140">priority</span></span>|<span data-ttu-id="45078-141">消息优先级</span><span class="sxs-lookup"><span data-stu-id="45078-141">Message Priority</span></span>|  
|<span data-ttu-id="45078-142">队列</span><span class="sxs-lookup"><span data-stu-id="45078-142">queue</span></span>|<span data-ttu-id="45078-143">目标队列</span><span class="sxs-lookup"><span data-stu-id="45078-143">Destination Queue</span></span>|  
|<span data-ttu-id="45078-144">recoverable</span><span class="sxs-lookup"><span data-stu-id="45078-144">recoverable</span></span>|<span data-ttu-id="45078-145">Recoverable</span><span class="sxs-lookup"><span data-stu-id="45078-145">Recoverable</span></span>|  
|<span data-ttu-id="45078-146">segmentationSupport</span><span class="sxs-lookup"><span data-stu-id="45078-146">segmentationSupport</span></span>|<span data-ttu-id="45078-147">支持分段</span><span class="sxs-lookup"><span data-stu-id="45078-147">Support Segmentation</span></span>|  
|<span data-ttu-id="45078-148">sendBatchSize</span><span class="sxs-lookup"><span data-stu-id="45078-148">sendBatchSize</span></span>|<span data-ttu-id="45078-149">批大小</span><span class="sxs-lookup"><span data-stu-id="45078-149">Batch Size</span></span>|  
|<span data-ttu-id="45078-150">sendQueueName</span><span class="sxs-lookup"><span data-stu-id="45078-150">sendQueueName</span></span>|<span data-ttu-id="45078-151">目标队列</span><span class="sxs-lookup"><span data-stu-id="45078-151">Destination Queue</span></span>|  
|<span data-ttu-id="45078-152">timeOut</span><span class="sxs-lookup"><span data-stu-id="45078-152">timeOut</span></span>|<span data-ttu-id="45078-153">超时</span><span class="sxs-lookup"><span data-stu-id="45078-153">Timeout</span></span>|  
|<span data-ttu-id="45078-154">timeOutUnits</span><span class="sxs-lookup"><span data-stu-id="45078-154">timeOutUnits</span></span>|<span data-ttu-id="45078-155">超时单元</span><span class="sxs-lookup"><span data-stu-id="45078-155">Timeout Unit</span></span>|  
|<span data-ttu-id="45078-156">transactional</span><span class="sxs-lookup"><span data-stu-id="45078-156">transactional</span></span>|<span data-ttu-id="45078-157">事务性</span><span class="sxs-lookup"><span data-stu-id="45078-157">Transactional</span></span>|  
|<span data-ttu-id="45078-158">useAuthentication</span><span class="sxs-lookup"><span data-stu-id="45078-158">useAuthentication</span></span>|<span data-ttu-id="45078-159">使用身份验证</span><span class="sxs-lookup"><span data-stu-id="45078-159">Use Authentication</span></span>|  
|<span data-ttu-id="45078-160">useDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="45078-160">useDeadLetterQueue</span></span>|<span data-ttu-id="45078-161">使用死信队列</span><span class="sxs-lookup"><span data-stu-id="45078-161">Use Dead Letter Queue</span></span>|  
|<span data-ttu-id="45078-162">useJournalQueue</span><span class="sxs-lookup"><span data-stu-id="45078-162">useJournalQueue</span></span>|<span data-ttu-id="45078-163">使用日记队列</span><span class="sxs-lookup"><span data-stu-id="45078-163">Use Journal Queue</span></span>|  
|<span data-ttu-id="45078-164">userName</span><span class="sxs-lookup"><span data-stu-id="45078-164">userName</span></span>|<span data-ttu-id="45078-165">用户名</span><span class="sxs-lookup"><span data-stu-id="45078-165">User Name</span></span>|  
  
 <span data-ttu-id="45078-166">下表描述了 MSMQ 适配器的内部名称**接收**自定义属性。</span><span class="sxs-lookup"><span data-stu-id="45078-166">The following table describes the internal names of the MSMQ adapter **Receive** custom properties.</span></span>  
  
|<span data-ttu-id="45078-167">**接收自定义属性名称**</span><span class="sxs-lookup"><span data-stu-id="45078-167">**Receive custom property name**</span></span>|<span data-ttu-id="45078-168">**显示名称**</span><span class="sxs-lookup"><span data-stu-id="45078-168">**Display name**</span></span>|  
|--------------------------------------|----------------------|  
|<span data-ttu-id="45078-169">batchSize</span><span class="sxs-lookup"><span data-stu-id="45078-169">batchSize</span></span>|<span data-ttu-id="45078-170">批大小</span><span class="sxs-lookup"><span data-stu-id="45078-170">Batch Size</span></span>|  
|<span data-ttu-id="45078-171">密码</span><span class="sxs-lookup"><span data-stu-id="45078-171">Password</span></span>|<span data-ttu-id="45078-172">密码</span><span class="sxs-lookup"><span data-stu-id="45078-172">Password</span></span>|  
|<span data-ttu-id="45078-173">队列</span><span class="sxs-lookup"><span data-stu-id="45078-173">Queue</span></span>|<span data-ttu-id="45078-174">队列</span><span class="sxs-lookup"><span data-stu-id="45078-174">Queue</span></span>|  
|<span data-ttu-id="45078-175">serialProcessing</span><span class="sxs-lookup"><span data-stu-id="45078-175">serialProcessing</span></span>|<span data-ttu-id="45078-176">串行处理</span><span class="sxs-lookup"><span data-stu-id="45078-176">Serial Processing</span></span>|  
|<span data-ttu-id="45078-177">事务性</span><span class="sxs-lookup"><span data-stu-id="45078-177">Transactional</span></span>|<span data-ttu-id="45078-178">事务性</span><span class="sxs-lookup"><span data-stu-id="45078-178">Transactional</span></span>|  
|<span data-ttu-id="45078-179">userName</span><span class="sxs-lookup"><span data-stu-id="45078-179">userName</span></span>|<span data-ttu-id="45078-180">用户名</span><span class="sxs-lookup"><span data-stu-id="45078-180">User Name</span></span>|  
  
## <a name="sample-code"></a><span data-ttu-id="45078-181">示例代码</span><span class="sxs-lookup"><span data-stu-id="45078-181">Sample Code</span></span>  
 <span data-ttu-id="45078-182">下面的 C# 程序为 MSMQ 适配器创建了单个接收位置。</span><span class="sxs-lookup"><span data-stu-id="45078-182">The following C# program creates a single receive location for the MSMQ adapter.</span></span> <span data-ttu-id="45078-183">该程序假定接收端口 ReceivePort1 存在，且使用 Helper 函数对自定义属性进行编码和格式化。</span><span class="sxs-lookup"><span data-stu-id="45078-183">It assumes that the receive port, ReceivePort1, exists and uses a helper function to encode and format the custom properties.</span></span>  
  
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