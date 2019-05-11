---
title: 将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d71e161-addc-47d4-9103-3655f3fb0b0d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2a08982e8e58e9333c52121b9be9da4aecd7f37
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376828"
---
# <a name="adding-the-oracle-database-adapter-to-biztalk-server-administration-console"></a><span data-ttu-id="0a30f-102">将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台</span><span class="sxs-lookup"><span data-stu-id="0a30f-102">Adding the Oracle Database Adapter to BizTalk Server Administration Console</span></span>
<span data-ttu-id="0a30f-103">本主题说明了如何添加 Wcf-oracledb 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0a30f-103">This topic provides instructions on how to add the WCF-OracleDB adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0a30f-104">如果你想要配置 WCF 自定义端口，则不需要执行这些任务[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0a30f-104">You need not perform these tasks if you want to configure a WCF-Custom port for the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="add-the-oracle-database-adapter"></a><span data-ttu-id="0a30f-105">添加 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="0a30f-105">Add the Oracle Database Adapter</span></span>  
  
1. <span data-ttu-id="0a30f-106">打开[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="0a30f-106">Open the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="0a30f-107">展开**BizTalk 组**，展开**平台设置**，然后选择**适配器**。</span><span class="sxs-lookup"><span data-stu-id="0a30f-107">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  
  
3. <span data-ttu-id="0a30f-108">右键单击**适配器**，选择**新建**，然后选择**适配器**。</span><span class="sxs-lookup"><span data-stu-id="0a30f-108">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  
  
    <span data-ttu-id="0a30f-109">![将适配器添加](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="0a30f-109">![Add an adapter](../../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4. <span data-ttu-id="0a30f-110">在中**适配器属性**对话框框中，输入名称适配器，从**适配器**列表中，选择**Wcf-oracledb**。</span><span class="sxs-lookup"><span data-stu-id="0a30f-110">In the **Adapter Properties** dialog box, enter a name for the adapter and from the **Adapter** list, select **WCF-OracleDB**.</span></span>  
  
    <span data-ttu-id="0a30f-111">![添加 WCF&#45;OracleDB 适配器添加到 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/media/wcf-oracledb.gif "WCF_OracleDB")</span><span class="sxs-lookup"><span data-stu-id="0a30f-111">![Adding WCF&#45;OracleDB adapter to BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/media/wcf-oracledb.gif "WCF_OracleDB")</span></span>  
  
5. <span data-ttu-id="0a30f-112">选择 **确定**。</span><span class="sxs-lookup"><span data-stu-id="0a30f-112">Select **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a30f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a30f-113">See Also</span></span>  
[<span data-ttu-id="0a30f-114">若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="0a30f-114">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)