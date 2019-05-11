---
title: 使用 IPv6 寻址的 BizTalk 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93cd2ead-5e87-47ac-8f78-d56b80afd34e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82dd615f5da897ae3091fc4742e97e28b1651a59
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246453"
---
# <a name="using-ipv6-addressing-with-biztalk-adapters"></a><span data-ttu-id="157ca-102">使用 IPv6 寻址的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="157ca-102">Using IPv6 Addressing with BizTalk Adapters</span></span>
<span data-ttu-id="157ca-103">BizTalk Server 适配器支持使用 IPv6 寻址。</span><span class="sxs-lookup"><span data-stu-id="157ca-103">BizTalk Server adapters support the use of IPv6 addressing.</span></span> <span data-ttu-id="157ca-104">本主题介绍了应该用于指定 UNC 路径，使用 HTTP 和 SOAP 适配器指定文本 IPv6 地址，以及如何使用 IPv6 范围标识符的命名法的 IPv6 地址命名法。</span><span class="sxs-lookup"><span data-stu-id="157ca-104">This topic describes the nomenclature that should be used to specify an IPv6 address for a UNC path, the nomenclature for specifying a literal IPv6 address, and the use of IPv6 scope identifiers with the HTTP and SOAP adapters.</span></span>  
  
## <a name="ipv6-address-nomenclature-used-for-a-unc-path"></a><span data-ttu-id="157ca-105">用于 UNC 路径的 IPv6 地址命名法</span><span class="sxs-lookup"><span data-stu-id="157ca-105">IPv6 Address Nomenclature Used for a UNC Path</span></span>  
 <span data-ttu-id="157ca-106">在 UNC 路径中指定文本 IPv6 地址时，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="157ca-106">Follow these steps when specifying a literal IPv6 address in a UNC path:</span></span>  
  
1. <span data-ttu-id="157ca-107">替换任何冒号":"字符替换短划线"-"字符。</span><span class="sxs-lookup"><span data-stu-id="157ca-107">Replace any colon ":" characters with a dash "-" character.</span></span>  
  
2. <span data-ttu-id="157ca-108">将文本追加"**ipv6-literal.net**"的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="157ca-108">Append the text "**.ipv6-literal.net**" to the IP address.</span></span>  
  
   <span data-ttu-id="157ca-109">例如，命名法是指向具有 IPv6 地址 2001:db8:2a:1005:230:48ff:fe73:989d 的计算机上的文件共享的 URI:</span><span class="sxs-lookup"><span data-stu-id="157ca-109">For example, the nomenclature for a URI that points to a file share on a computer with the IPv6 address 2001:DB8:2a:1005:230:48ff:fe73:989d would be:</span></span>  
  
```  
\\2001-DB8-2a-1005-230-48ff-fe73-989d.ipv6-literal.net\<sharename\>  
```  
  
 <span data-ttu-id="157ca-110">其中\< *sharename* \>是目标计算机上的文件共享的名称。</span><span class="sxs-lookup"><span data-stu-id="157ca-110">Where \<*sharename*\> is the name of the file share on the target computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="157ca-111">请确保主机实例的文件发送和接收处理程序中运行的用户帐户具有访问文件共享的适当权限。</span><span class="sxs-lookup"><span data-stu-id="157ca-111">Ensure that the user accounts for the host instances that the File send and receive handlers are running in have appropriate permissions to the file share.</span></span> <span data-ttu-id="157ca-112">与文件适配器接收文件所需的文件夹权限的详细信息请参阅[配置文件接收处理程序](../core/configure-the-file-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="157ca-112">For more information about the folder permissions required to receive files with the File adapter see [Configure a File Receive Handler](../core/configure-the-file-adapter.md).</span></span> <span data-ttu-id="157ca-113">发送与文件适配器的文件时所需的文件夹权限的详细信息请参阅[与文件适配器的已知问题](../core/known-issues-with-the-file-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="157ca-113">For more information about the folder permissions required when sending files with the File adapter see [Known Issues with the File Adapter](../core/known-issues-with-the-file-adapter.md).</span></span> <span data-ttu-id="157ca-114">有关支持与文件适配器一起使用的文件系统的信息，请参阅[ http://support.microsoft.com/kb/815070 ](http://support.microsoft.com/kb/815070)。</span><span class="sxs-lookup"><span data-stu-id="157ca-114">For information about the file systems that are supported for use with the File adapter, see [http://support.microsoft.com/kb/815070](http://support.microsoft.com/kb/815070).</span></span>  
  
## <a name="using-ipv6-scope-identifiers-with-the-http-adapter-and-the-soap-send-adapter"></a><span data-ttu-id="157ca-115">使用 HTTP 适配器和 SOAP 发送适配器使用 IPv6 范围标识符</span><span class="sxs-lookup"><span data-stu-id="157ca-115">Using IPv6 Scope Identifiers with the HTTP Adapter and the SOAP Send Adapter</span></span>  
 <span data-ttu-id="157ca-116">HTTP 发送和接收适配器和 SOAP 发送适配器要求，如果 IPv6 地址中使用的范围标识符，则该范围标识符必须使用转义码转义 **%25**。</span><span class="sxs-lookup"><span data-stu-id="157ca-116">The HTTP send and receive adapter and the SOAP send adapter require that if a scope identifier is used in an IPv6 address, the scope identifier must be escaped with the escape code **%25**.</span></span> <span data-ttu-id="157ca-117">例如， **fe80::550c:489f:e65e:aef3%8**是有效的 IPv6 地址包含范围标识符 (%8)。</span><span class="sxs-lookup"><span data-stu-id="157ca-117">For example, **fe80::550c:489f:e65e:aef3%8** is a valid IPv6 address containing a scope identifier (%8).</span></span> <span data-ttu-id="157ca-118">若要将此 IPv6 地址用于 HTTP 发送和接收适配器或 SOAP 发送适配器，该范围标识符必须进行转义，如下所示：</span><span class="sxs-lookup"><span data-stu-id="157ca-118">To use this IPv6 address with the HTTP send and receive adapters or the SOAP send adapter, the scope identifier must be escaped as follows:</span></span>  
  
```  
fe80::550c:489f:e65e:aef3%258  
```  
  
## <a name="adapter-uri-nomenclature-used-for-a-literal-ipv6-address"></a><span data-ttu-id="157ca-119">用于文本 IPv6 地址的适配器 URI 命名法</span><span class="sxs-lookup"><span data-stu-id="157ca-119">Adapter URI Nomenclature Used for a Literal IPv6 Address</span></span>  
  
-   <span data-ttu-id="157ca-120">若要使用文本 IPv6 地址用于适配器 URI，请将 IP 地址括在方括号"["、"]"。</span><span class="sxs-lookup"><span data-stu-id="157ca-120">To use a literal IPv6 address for an adapter URI, enclose the IP address in square brackets "[", "]".</span></span> <span data-ttu-id="157ca-121">例如，将为使用 IPv6 地址 2001:db8:2a:1005:230:48ff:fe73:989d 的 URI 的命名法：</span><span class="sxs-lookup"><span data-stu-id="157ca-121">For example, the nomenclature for a URI with the IPv6 address 2001:DB8:2a:1005:230:48ff:fe73:989d would be:</span></span>  
  
    ```  
    [2001:DB8:2a:1005:230:48ff:fe73:989d]  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="157ca-122">将文本 IPv6 地址用于适配器 Uri 应遵循中确立的准则[RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375)。</span><span class="sxs-lookup"><span data-stu-id="157ca-122">The use of literal IPv6 addresses for adapter URIs follows the guidelines established in [RFC2732](http://go.microsoft.com/fwlink/?LinkId=90375).</span></span>  
  
-   <span data-ttu-id="157ca-123">当指定文本 IPv6 地址作为服务器名称，来为 POP3 接收适配器、 SMTP 发送适配器，或 SQL 发送和接收适配器，但是的 IPv6 地址不应括在方括号中。</span><span class="sxs-lookup"><span data-stu-id="157ca-123">When specifying a literal IPv6 address as the server name for the POP3 receive adapter, the SMTP send adapter, or the SQL send and receive adapters, the IPv6 address should not be enclosed in square brackets.</span></span>  
  
## <a name="summary-of-considerations-when-using-literal-ipv6-addressing-with-biztalk-adapters"></a><span data-ttu-id="157ca-124">使用文本 IPv6 寻址的 BizTalk 适配器时的注意事项的摘要</span><span class="sxs-lookup"><span data-stu-id="157ca-124">Summary of Considerations When Using Literal IPv6 Addressing with BizTalk Adapters</span></span>  
 <span data-ttu-id="157ca-125">下表总结了当使用文本 IPv6 地址需要的 IP 地址括在方括号"["、"]"和一个 IPv6 地址中使用的范围标识符时必须进行转义：</span><span class="sxs-lookup"><span data-stu-id="157ca-125">The table below summarizes when the use of a literal IPv6 address requires that the IP address is enclosed in square brackets "[", "]" and when a scope identifier that is used in an IPv6 address must be escaped:</span></span>  
  
|<span data-ttu-id="157ca-126">适配器</span><span class="sxs-lookup"><span data-stu-id="157ca-126">Adapter</span></span>|<span data-ttu-id="157ca-127">要求，将文本 IPv6 地址括在方括号内吗？</span><span class="sxs-lookup"><span data-stu-id="157ca-127">Requires that literal IPv6 address is enclosed in square brackets?</span></span>|<span data-ttu-id="157ca-128">需要该范围标识符进行转义？</span><span class="sxs-lookup"><span data-stu-id="157ca-128">Requires that scope identifier is escaped?</span></span>|  
|---|---|---|  
|<span data-ttu-id="157ca-129">POP3 接收</span><span class="sxs-lookup"><span data-stu-id="157ca-129">POP3 receive</span></span>|<span data-ttu-id="157ca-130">否</span><span class="sxs-lookup"><span data-stu-id="157ca-130">No</span></span>|<span data-ttu-id="157ca-131">否</span><span class="sxs-lookup"><span data-stu-id="157ca-131">No</span></span>|  
|<span data-ttu-id="157ca-132">SMTP 发送</span><span class="sxs-lookup"><span data-stu-id="157ca-132">SMTP send</span></span>|<span data-ttu-id="157ca-133">否</span><span class="sxs-lookup"><span data-stu-id="157ca-133">No</span></span>|<span data-ttu-id="157ca-134">否</span><span class="sxs-lookup"><span data-stu-id="157ca-134">No</span></span>|  
|<span data-ttu-id="157ca-135">SQL 发送和接收</span><span class="sxs-lookup"><span data-stu-id="157ca-135">SQL send and receive</span></span>|<span data-ttu-id="157ca-136">否</span><span class="sxs-lookup"><span data-stu-id="157ca-136">No</span></span>|<span data-ttu-id="157ca-137">否</span><span class="sxs-lookup"><span data-stu-id="157ca-137">No</span></span>|  
|<span data-ttu-id="157ca-138">文件发送和接收</span><span class="sxs-lookup"><span data-stu-id="157ca-138">File send and receive</span></span>|<span data-ttu-id="157ca-139">否 (请参阅部分**IPv6 地址命名法用于 UNC 路径**)</span><span class="sxs-lookup"><span data-stu-id="157ca-139">No (see section **IPv6 Address Nomenclature Used for a UNC Path**)</span></span>|<span data-ttu-id="157ca-140">否</span><span class="sxs-lookup"><span data-stu-id="157ca-140">No</span></span>|  
|<span data-ttu-id="157ca-141">HTTP 发送和接收</span><span class="sxs-lookup"><span data-stu-id="157ca-141">HTTP send and receive</span></span>|<span data-ttu-id="157ca-142">是</span><span class="sxs-lookup"><span data-stu-id="157ca-142">Yes</span></span>|<span data-ttu-id="157ca-143">是</span><span class="sxs-lookup"><span data-stu-id="157ca-143">Yes</span></span>|  
|<span data-ttu-id="157ca-144">MQSeries 发送和接收</span><span class="sxs-lookup"><span data-stu-id="157ca-144">MQSeries send and receive</span></span>|<span data-ttu-id="157ca-145">是</span><span class="sxs-lookup"><span data-stu-id="157ca-145">Yes</span></span>|<span data-ttu-id="157ca-146">否</span><span class="sxs-lookup"><span data-stu-id="157ca-146">No</span></span>|  
|<span data-ttu-id="157ca-147">MSMQ 发送和接收</span><span class="sxs-lookup"><span data-stu-id="157ca-147">MSMQ send and receive</span></span>|<span data-ttu-id="157ca-148">是</span><span class="sxs-lookup"><span data-stu-id="157ca-148">Yes</span></span>|<span data-ttu-id="157ca-149">否</span><span class="sxs-lookup"><span data-stu-id="157ca-149">No</span></span>|  
|<span data-ttu-id="157ca-150">SOAP 发送</span><span class="sxs-lookup"><span data-stu-id="157ca-150">SOAP send</span></span>|<span data-ttu-id="157ca-151">是</span><span class="sxs-lookup"><span data-stu-id="157ca-151">Yes</span></span>|<span data-ttu-id="157ca-152">是</span><span class="sxs-lookup"><span data-stu-id="157ca-152">Yes</span></span>|  
|<span data-ttu-id="157ca-153">SOAP 接收</span><span class="sxs-lookup"><span data-stu-id="157ca-153">SOAP receive</span></span>|<span data-ttu-id="157ca-154">是</span><span class="sxs-lookup"><span data-stu-id="157ca-154">Yes</span></span>|<span data-ttu-id="157ca-155">否</span><span class="sxs-lookup"><span data-stu-id="157ca-155">No</span></span>|  
|<span data-ttu-id="157ca-156">WCF 发送和接收</span><span class="sxs-lookup"><span data-stu-id="157ca-156">WCF send and receive</span></span>|<span data-ttu-id="157ca-157">是</span><span class="sxs-lookup"><span data-stu-id="157ca-157">Yes</span></span>|<span data-ttu-id="157ca-158">否</span><span class="sxs-lookup"><span data-stu-id="157ca-158">No</span></span>|