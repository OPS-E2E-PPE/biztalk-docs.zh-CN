---
title: 如何查看架构的架构定义 (XSD) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, viewing
- managing [schemas], viewing
- viewing, schema definitions
- schemas, schema definition (XSD)
- managing [schemas], schema definition (XSD)
ms.assetid: 21b6d9e6-5737-4334-9fe6-15ae01f90c0d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 941951398ec966dea0045283e13c4581f60016aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256437"
---
# <a name="how-to-view-the-schema-definition-xsd-of-a-schema"></a><span data-ttu-id="6601e-102">如何查看某一架构的架构定义 (XSD)</span><span class="sxs-lookup"><span data-stu-id="6601e-102">How to View the Schema Definition (XSD) of a Schema</span></span>
<span data-ttu-id="6601e-103">本主题介绍如何使用 BizTalk Server 管理控制台来查看某一架构的架构定义 (XSD)。</span><span class="sxs-lookup"><span data-stu-id="6601e-103">This topic describes how to use the BizTalk Server Administration console to view the schema definition (XSD) of a schema.</span></span> <span data-ttu-id="6601e-104">您可能要查看架构定义以排除架构验证错误或验证部署了正确的架构。</span><span class="sxs-lookup"><span data-stu-id="6601e-104">You might want to do this to troubleshoot schema validation errors or validate that the correct schema is deployed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6601e-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="6601e-105">Prerequisites</span></span>  
 <span data-ttu-id="6601e-106">若要执行本主题中描述的过程，必须以 BizTalk Server Administrators 组或 BizTalk Server Operators 组成员的帐户身份登录。</span><span class="sxs-lookup"><span data-stu-id="6601e-106">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group or BizTalk Server Operators group.</span></span> <span data-ttu-id="6601e-107">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="6601e-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-the-xsd-of-a-schema"></a><span data-ttu-id="6601e-108">查看架构的 XSD</span><span class="sxs-lookup"><span data-stu-id="6601e-108">To view the XSD of a schema</span></span>  
  
1.  <span data-ttu-id="6601e-109">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="6601e-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6601e-110">在控制台树中，展开**BizTalk Server 管理**，展开包含你想要查看下面的 XSD 的架构的 BizTalk 组，然后展开包含架构的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6601e-110">In the console tree, expand **BizTalk Server Administration**, expand the BizTalk group containing the schema for which you want to view the XSD, and then expand the application containing the schema.</span></span>  
  
3.  <span data-ttu-id="6601e-111">单击**架构**，右键单击的架构，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="6601e-111">Click **Schemas**, right-click the schema, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="6601e-112">在左窗格中，单击**架构视图**。</span><span class="sxs-lookup"><span data-stu-id="6601e-112">In the left pane, click **Schema View**.</span></span>  
  
     <span data-ttu-id="6601e-113">该 XSD 将显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="6601e-113">The XSD displays in the right pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6601e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6601e-114">See Also</span></span>  
 [<span data-ttu-id="6601e-115">管理架构</span><span class="sxs-lookup"><span data-stu-id="6601e-115">Managing Schemas</span></span>](../core/managing-schemas.md)