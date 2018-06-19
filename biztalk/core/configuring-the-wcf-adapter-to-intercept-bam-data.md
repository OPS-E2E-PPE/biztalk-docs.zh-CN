---
title: 配置 WCF 适配器以截获 BAM 数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cd705c27-5d04-47e5-9bb2-61235f8fe544
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f418512ecd0a3e38f884965d1698579fb300dd74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232765"
---
# <a name="configuring-the-wcf-adapter-to-intercept-bam-data"></a><span data-ttu-id="057f1-102">配置 WCF 适配器以侦听 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="057f1-102">Configuring the WCF Adapter to Intercept BAM Data</span></span>
<span data-ttu-id="057f1-103">本部分包含为配置 BizTalk WCF 适配器以便与 BAM WCF 侦听器一起运行而必须执行的步骤的相关信息。</span><span class="sxs-lookup"><span data-stu-id="057f1-103">This section contains information about the steps you must take to configure the BizTalk WCF adapter to work with the BAM WCF interceptor.</span></span>  
  
 <span data-ttu-id="057f1-104">基本步骤如下所述：</span><span class="sxs-lookup"><span data-stu-id="057f1-104">The basic steps are as follows:</span></span>  
  
-   <span data-ttu-id="057f1-105">将 BAM 行为添加到 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="057f1-105">Add the BAM behavior to the machine.config file.</span></span>  
  
-   <span data-ttu-id="057f1-106">创建 BizTalk WCF 适配器。</span><span class="sxs-lookup"><span data-stu-id="057f1-106">Create a BizTalk WCF adapter.</span></span>  
  
-   <span data-ttu-id="057f1-107">配置 BAM WCF 侦听。</span><span class="sxs-lookup"><span data-stu-id="057f1-107">Configure the BAM WCF interception.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="057f1-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="057f1-108">In This Section</span></span>  
  
-   [<span data-ttu-id="057f1-109">如何将 BAM 侦听器行为添加到 Machine.config 文件</span><span class="sxs-lookup"><span data-stu-id="057f1-109">How to Add the BAM Interceptor Behavior to the Machine.config File</span></span>](../core/how-to-add-the-bam-interceptor-behavior-to-the-machine-config-file.md)  
  
-   [<span data-ttu-id="057f1-110">如何为 BizTalk Server 中创建的 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="057f1-110">How to Create a WCF Adapter for BizTalk Server</span></span>](../core/how-to-create-a-wcf-adapter-for-biztalk-server.md)  
  
-   [<span data-ttu-id="057f1-111">如何配置接收和 BAM WCF 侦听发送位置和端口</span><span class="sxs-lookup"><span data-stu-id="057f1-111">How to Configure Receive and Send Locations and Ports for BAM WCF Interception</span></span>](../core/how-to-configure-receive-and-send-locations-and-ports-for-bam-wcf-interception.md)  
  
-   [<span data-ttu-id="057f1-112">如何配置 BAM WCF 截获</span><span class="sxs-lookup"><span data-stu-id="057f1-112">How to Configure the BAM WCF Interception</span></span>](../core/how-to-configure-the-bam-wcf-interception.md)  
  
-   [<span data-ttu-id="057f1-113">使用错误处理</span><span class="sxs-lookup"><span data-stu-id="057f1-113">Using Fault Handling</span></span>](../core/using-fault-handling.md)