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
ms.openlocfilehash: fc036be84bb64e794e6109e1ebc4ec730f382878
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023107"
---
# <a name="testing-schemas"></a><span data-ttu-id="0c80a-102">测试架构</span><span class="sxs-lookup"><span data-stu-id="0c80a-102">Testing Schemas</span></span>
<span data-ttu-id="0c80a-103">在创建架构之后，您可能希望验证该架构的 XML 结构符合您的要求。</span><span class="sxs-lookup"><span data-stu-id="0c80a-103">After you have created your schema, you may want to validate that it describes the XML structure you intend it to describe.</span></span> <span data-ttu-id="0c80a-104">您可以对架构执行以下三种操作以进行验证：</span><span class="sxs-lookup"><span data-stu-id="0c80a-104">You can perform the following three operations on your schema to validate it:</span></span>  
  
- <span data-ttu-id="0c80a-105">**实例生成**。</span><span class="sxs-lookup"><span data-stu-id="0c80a-105">**Instance generation**.</span></span> <span data-ttu-id="0c80a-106">此操作将从架构生成实例消息，创建要显示由该架构指定的 XML 元素和属性的测试数据。</span><span class="sxs-lookup"><span data-stu-id="0c80a-106">This operation generates an instance message from a schema, creating test data to accompany the XML elements and attributes specified by the schema.</span></span>  
  
- <span data-ttu-id="0c80a-107">**架构验证**。</span><span class="sxs-lookup"><span data-stu-id="0c80a-107">**Schema validation**.</span></span> <span data-ttu-id="0c80a-108">此操作将验证架构的内部一致性，确保它符合 XML 架构定义 (XSD) 语言架构标准。</span><span class="sxs-lookup"><span data-stu-id="0c80a-108">This operation validates the internal consistency of a schema, assuring that it conforms to the XML Schema definition (XSD) language schema standard.</span></span>  
  
- <span data-ttu-id="0c80a-109">**实例验证**。</span><span class="sxs-lookup"><span data-stu-id="0c80a-109">**Instance validation**.</span></span> <span data-ttu-id="0c80a-110">此操作将依据架构验证给定的实例消息。</span><span class="sxs-lookup"><span data-stu-id="0c80a-110">This operation validates a given instance message against a schema.</span></span>  
  
  <span data-ttu-id="0c80a-111">对于在生产环境中使用架构之前测试该架构，所有这三种操作都非常有用。</span><span class="sxs-lookup"><span data-stu-id="0c80a-111">All three of these operations are useful for testing your schemas before putting them into use in a production environment.</span></span>  
  
  <span data-ttu-id="0c80a-112">本部分较详细地介绍了这些操作。</span><span class="sxs-lookup"><span data-stu-id="0c80a-112">This section describes these operations in greater detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0c80a-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="0c80a-113">In This Section</span></span>  
  
-   [<span data-ttu-id="0c80a-114">如何在 Visual Studio 中的架构验证</span><span class="sxs-lookup"><span data-stu-id="0c80a-114">How to Validate Schemas in Visual Studio</span></span>](../core/how-to-validate-schemas-in-visual-studio.md)  
  
-   [<span data-ttu-id="0c80a-115">如何验证实例消息</span><span class="sxs-lookup"><span data-stu-id="0c80a-115">How to Validate Instance Messages</span></span>](../core/how-to-validate-instance-messages.md)  
  
-   [<span data-ttu-id="0c80a-116">如何生成实例消息</span><span class="sxs-lookup"><span data-stu-id="0c80a-116">How to Generate Instance Messages</span></span>](../core/how-to-generate-instance-messages.md)