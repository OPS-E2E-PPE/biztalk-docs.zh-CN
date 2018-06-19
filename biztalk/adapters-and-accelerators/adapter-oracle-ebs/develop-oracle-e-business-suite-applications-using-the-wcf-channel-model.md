---
title: 开发 Oracle E-business Suite 应用程序使用 WCF 通道模型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75bb6de1-e11a-4377-af13-e1cb954aaf3f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e99dfa0c69500b86fe086ce0daa81e3ffb62857d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214797"
---
# <a name="develop-oracle-e-business-suite-applications-using-the-wcf-channel-model"></a><span data-ttu-id="4ad1f-102">开发 Oracle E-business Suite 应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="4ad1f-102">Develop Oracle E-Business Suite applications using the WCF Channel Model</span></span>
<span data-ttu-id="4ad1f-103">你可以使用[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]通道模型来使用[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]通过直接通过使用 Oracle EBS 绑定创建的通道实例发送 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="4ad1f-103">You can use the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] channel model to consume the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] by sending XML messages directly over a channel instance created with the Oracle EBS Binding.</span></span>  
  
 <span data-ttu-id="4ad1f-104">通过使用的强类型类和 WCF 服务模型公开是通道模型提供更好地控制细化 Oracle E-business Suite 执行的操作的方法使用 WCF 通道模型的一个优点。</span><span class="sxs-lookup"><span data-stu-id="4ad1f-104">One advantage of using the WCF channel model over using the strongly-typed classes and methods that the WCF service model exposes is that the channel model provides more fine-grained control over the operations that you perform on the Oracle E-Business Suite.</span></span> <span data-ttu-id="4ad1f-105">此控件来自在 WCF 通道模型中，你直接控制通过通道发送的消息的内容的事实。</span><span class="sxs-lookup"><span data-stu-id="4ad1f-105">This control comes from the fact that in the WCF channel model, you directly control the contents of the messages that you send over the channel.</span></span>  
  
 <span data-ttu-id="4ad1f-106">在某些情况下，此额外级别是控制的有益的。</span><span class="sxs-lookup"><span data-stu-id="4ad1f-106">In certain scenarios, this extra level of control can be beneficial.</span></span> <span data-ttu-id="4ad1f-107">例如，当使用 WCF 通道模型来执行更新操作在表上的，你有选择地可以直接更新目标行中的列，通过省略消息中传递的更新模板中的列。</span><span class="sxs-lookup"><span data-stu-id="4ad1f-107">For example, when you use the WCF channel model to perform an Update operation on a table, you can selectively update columns in the target rows by omitting columns from the update template that you pass in the message.</span></span> <span data-ttu-id="4ad1f-108">仅有的列所需那些带有"nillable = false"WSDL 中。</span><span class="sxs-lookup"><span data-stu-id="4ad1f-108">The only columns that are required are those with “nillable=false” in the WSDL.</span></span> <span data-ttu-id="4ad1f-109">由公开的更新方法[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]客户端对于表架构中包含的每个列的模板使用强类型的记录参数。</span><span class="sxs-lookup"><span data-stu-id="4ad1f-109">The update method exposed by a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] client uses a strongly-typed record parameter for the template that includes every column in the table schema.</span></span>  
  
 <span data-ttu-id="4ad1f-110">本部分中的主题说明如何执行操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="4ad1f-110">The topics in this section explain how to perform operations on the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] by using the WCF channel model.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4ad1f-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="4ad1f-111">In This Section</span></span>  
  
-   [<span data-ttu-id="4ad1f-112">与 Oracle E-business Suite 适配器的 WCF 通道模型概述</span><span class="sxs-lookup"><span data-stu-id="4ad1f-112">Overview of the WCF channel model with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/overview-of-the-wcf-channel-model-with-the-oracle-e-business-suite-adapter.md)  
  
-   [<span data-ttu-id="4ad1f-113">创建一个通道，使用 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="4ad1f-113">Create a channel using Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-channel-using-oracle-e-business-suite.md)
  
-   [<span data-ttu-id="4ad1f-114">在 Oracle E-business Suite 使用 WCF 通道模型运行接口表上的 insert 操作</span><span class="sxs-lookup"><span data-stu-id="4ad1f-114">Run an insert operation on an interface table in Oracle E-Business Suite using the WCF channel model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/insert-on-an-interface-table-in-oracle-ebs-using-the-wcf-channel-model.md)  
  
-   [<span data-ttu-id="4ad1f-115">轮询 Oracle E-business Suite SELECT 语句中使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="4ad1f-115">Poll Oracle E-Business Suite using SELECT statement with the WCF channel model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/poll-oracle-e-business-suite-using-select-statement-with-the-wcf-channel-model.md)
  
## <a name="see-also"></a><span data-ttu-id="4ad1f-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ad1f-116">See Also</span></span>  
[<span data-ttu-id="4ad1f-117">开发 Oracle E-business Suite 应用程序</span><span class="sxs-lookup"><span data-stu-id="4ad1f-117">Develop your Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)