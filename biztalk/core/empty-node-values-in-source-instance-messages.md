---
title: 源中的空节点值实例消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76f9d7c8-5a82-41e9-9077-7b1ddd80a837
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d847aace487d7b7ebd472ec96173e38315df529
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976614"
---
# <a name="empty-node-values-in-source-instance-messages"></a><span data-ttu-id="a9475-102">源实例消息中的空节点值</span><span class="sxs-lookup"><span data-stu-id="a9475-102">Empty Node Values in Source Instance Messages</span></span>
<span data-ttu-id="a9475-103">在测试映射时，有时可能并不需要全部 schema 节点中的内容。</span><span class="sxs-lookup"><span data-stu-id="a9475-103">There may be times when you do not want content in all of the schema nodes when you test a map.</span></span>  

## <a name="ceate-empty-node-values"></a><span data-ttu-id="a9475-104">请空节点值</span><span class="sxs-lookup"><span data-stu-id="a9475-104">Ceate empty node values</span></span>  

1. <span data-ttu-id="a9475-105">使用 BizTalk 编辑器生成实例数据。</span><span class="sxs-lookup"><span data-stu-id="a9475-105">Generate instance data using BizTalk Editor.</span></span> <span data-ttu-id="a9475-106">有关生成实例数据的详细信息，请参阅[如何生成实例消息](../core/how-to-generate-instance-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="a9475-106">For more information about generating instance data, see [How to Generate Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  

2. <span data-ttu-id="a9475-107">在文本编辑器中打开输入实例消息，删除希望为空的元素和属性中的数据，然后保存修改后的实例文件。</span><span class="sxs-lookup"><span data-stu-id="a9475-107">Open the input instance message in a text editor, delete the data from elements and attributes that you want to be empty, and then save the modified instance file.</span></span>  

3. <span data-ttu-id="a9475-108">在验证和测试架构之后，配置 BizTalk 映射器以使用刚刚修改过的文件。</span><span class="sxs-lookup"><span data-stu-id="a9475-108">Configure BizTalk Mapper to use the file you just modified when the schema is validated and tested.</span></span> <span data-ttu-id="a9475-109">在“属性”窗口中设置用于架构的文件。</span><span class="sxs-lookup"><span data-stu-id="a9475-109">You set the file in the Properties window for the schema.</span></span> <span data-ttu-id="a9475-110">有关设置属性的详细信息，请参阅**映射文件属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="a9475-110">For more information about setting properties, see **Map File Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="a9475-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="a9475-111">See Also</span></span>  
- [<span data-ttu-id="a9475-112">如何生成实例消息</span><span class="sxs-lookup"><span data-stu-id="a9475-112">How to Generate Instance Messages</span></span>](../core/how-to-generate-instance-messages.md)   
- <span data-ttu-id="a9475-113">**架构属性参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="a9475-113">**Schema Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
