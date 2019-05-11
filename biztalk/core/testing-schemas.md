---
title: 测试架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2e28b7c-9d0c-4336-8bee-4599d41a57f4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8331026992e9715793cf366409cb68904e5058c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298973"
---
# <a name="testing-schemas"></a><span data-ttu-id="51716-102">测试架构</span><span class="sxs-lookup"><span data-stu-id="51716-102">Testing Schemas</span></span>
<span data-ttu-id="51716-103">创建您的架构后，您可能想要验证它想要介绍的 XML 结构。</span><span class="sxs-lookup"><span data-stu-id="51716-103">After you have created your schema, you may want to validate that it describes the XML structure you intend it to describe.</span></span> <span data-ttu-id="51716-104">您可以执行您对其进行验证的架构上的以下三个操作：</span><span class="sxs-lookup"><span data-stu-id="51716-104">You can perform the following three operations on your schema to validate it:</span></span>  
  
- <span data-ttu-id="51716-105">**实例生成**。</span><span class="sxs-lookup"><span data-stu-id="51716-105">**Instance generation**.</span></span> <span data-ttu-id="51716-106">此操作将从创建测试数据随附的 XML 元素和属性架构指定的架构生成实例消息。</span><span class="sxs-lookup"><span data-stu-id="51716-106">This operation generates an instance message from a schema, creating test data to accompany the XML elements and attributes specified by the schema.</span></span>  
  
- <span data-ttu-id="51716-107">**架构验证**。</span><span class="sxs-lookup"><span data-stu-id="51716-107">**Schema validation**.</span></span> <span data-ttu-id="51716-108">此操作将验证架构，确保它符合 XML 架构定义 (XSD) 语言架构标准的内部一致性。</span><span class="sxs-lookup"><span data-stu-id="51716-108">This operation validates the internal consistency of a schema, assuring that it conforms to the XML Schema definition (XSD) language schema standard.</span></span>  
  
- <span data-ttu-id="51716-109">**实例验证**。</span><span class="sxs-lookup"><span data-stu-id="51716-109">**Instance validation**.</span></span> <span data-ttu-id="51716-110">此操作将验证架构针对给定的实例消息。</span><span class="sxs-lookup"><span data-stu-id="51716-110">This operation validates a given instance message against a schema.</span></span>  
  
  <span data-ttu-id="51716-111">所有这三种操作可用于之前将其放入生产环境中测试您的架构。</span><span class="sxs-lookup"><span data-stu-id="51716-111">All three of these operations are useful for testing your schemas before putting them into use in a production environment.</span></span>  
  
  <span data-ttu-id="51716-112">本部分介绍了更详细地介绍这些操作。</span><span class="sxs-lookup"><span data-stu-id="51716-112">This section describes these operations in greater detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="51716-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="51716-113">In This Section</span></span>  
  
-   [<span data-ttu-id="51716-114">如何在 Visual Studio 中的架构验证</span><span class="sxs-lookup"><span data-stu-id="51716-114">How to Validate Schemas in Visual Studio</span></span>](../core/how-to-validate-schemas-in-visual-studio.md)  
  
-   [<span data-ttu-id="51716-115">如何验证实例消息</span><span class="sxs-lookup"><span data-stu-id="51716-115">How to Validate Instance Messages</span></span>](../core/how-to-validate-instance-messages.md)  
  
-   [<span data-ttu-id="51716-116">如何生成实例消息</span><span class="sxs-lookup"><span data-stu-id="51716-116">How to Generate Instance Messages</span></span>](../core/how-to-generate-instance-messages.md)