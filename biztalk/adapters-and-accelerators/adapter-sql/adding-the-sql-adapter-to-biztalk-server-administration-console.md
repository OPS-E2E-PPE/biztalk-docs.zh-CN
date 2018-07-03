---
title: 将 SQL 适配器添加到 BizTalk Server 管理控制台 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd974f28-c9cb-46de-95be-83716231ebcd
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff3eb1aa8870316ec506a61658c34db6acc7f62c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005726"
---
# <a name="adding-the-sql-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="fd17c-102">将 SQL 适配器添加到 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="fd17c-102">Adding the SQL Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="fd17c-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以在 BizTalk 中可作为 WCF 自定义端口或 WCF SQL 端口使用。</span><span class="sxs-lookup"><span data-stu-id="fd17c-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-SQL port.</span></span> <span data-ttu-id="fd17c-104">如果你想要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过 WCF 自定义端口，您不需要添加到 WCF 自定义端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台，因为 WCF 自定义端口添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中的默认情况下。</span><span class="sxs-lookup"><span data-stu-id="fd17c-104">If you want to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="fd17c-105">但是，如果你想要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过 WCF SQL 端口，必须首先添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fd17c-105">However, if you want to use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] through a WCF-SQL port, you must first add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 <span data-ttu-id="fd17c-106">本主题说明如何将添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fd17c-106">This topic shows you how to add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fd17c-107">不需要执行以下步骤，如果你想要配置 WCF 自定义端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd17c-107">You do not need to follow these steps if you want to configure a WCF-Custom port for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="add-the-sql-adapter"></a><span data-ttu-id="fd17c-108">添加 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="fd17c-108">Add the SQL Adapter</span></span>  
  
1. <span data-ttu-id="fd17c-109">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="fd17c-109">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="fd17c-110">展开**BizTalk 组**，展开**平台设置**，然后选择**适配器**。</span><span class="sxs-lookup"><span data-stu-id="fd17c-110">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  
  
3. <span data-ttu-id="fd17c-111">右键单击**适配器**，依次指向**新建**，然后选择**适配器**。</span><span class="sxs-lookup"><span data-stu-id="fd17c-111">Right-click **Adapters**, point to **New**, and select **Adapter**.</span></span>  
  
    <span data-ttu-id="fd17c-112">![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="fd17c-112">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="fd17c-113">在中**适配器属性**对话框框中，输入的名称对于适配器，然后从**适配器**列表中，选择**WCF-SQL**。</span><span class="sxs-lookup"><span data-stu-id="fd17c-113">In the **Adapter Properties** dialog box, enter a name for the adapter, and from the **Adapter** list, select **WCF-SQL**.</span></span>  
  
    <span data-ttu-id="fd17c-114">![添加 WCF&#45;SQL 适配器添加到 BizTalk](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")</span><span class="sxs-lookup"><span data-stu-id="fd17c-114">![Add WCF&#45;SQL adapter to BizTalk](../../adapters-and-accelerators/adapter-sql/media/4c6e2650-5d3a-4de8-a60a-a136d93a6fcf.gif "4c6e2650-5d3a-4de8-a60a-a136d93a6fcf")</span></span>  
  
5. <span data-ttu-id="fd17c-115">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="fd17c-115">Select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd17c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd17c-116">See Also</span></span>  
 [<span data-ttu-id="fd17c-117">若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="fd17c-117">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)