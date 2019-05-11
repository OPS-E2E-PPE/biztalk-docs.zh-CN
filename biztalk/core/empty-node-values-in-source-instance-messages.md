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
ms.openlocfilehash: afaf714e3c979576939ebef8fdd39f283828cab7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350018"
---
# <a name="empty-node-values-in-source-instance-messages"></a><span data-ttu-id="79644-102">源实例消息中的空节点值</span><span class="sxs-lookup"><span data-stu-id="79644-102">Empty Node Values in Source Instance Messages</span></span>
<span data-ttu-id="79644-103">可能的有时你不想时中的所有架构节点的内容时测试映射。</span><span class="sxs-lookup"><span data-stu-id="79644-103">There may be times when you do not want content in all of the schema nodes when you test a map.</span></span>  

## <a name="ceate-empty-node-values"></a><span data-ttu-id="79644-104">请空节点值</span><span class="sxs-lookup"><span data-stu-id="79644-104">Ceate empty node values</span></span>  

1. <span data-ttu-id="79644-105">生成实例数据使用 BizTalk 编辑器。</span><span class="sxs-lookup"><span data-stu-id="79644-105">Generate instance data using BizTalk Editor.</span></span> <span data-ttu-id="79644-106">有关生成实例数据的详细信息，请参阅[如何生成实例消息](../core/how-to-generate-instance-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="79644-106">For more information about generating instance data, see [How to Generate Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  

2. <span data-ttu-id="79644-107">在文本编辑器中打开输入的实例消息从用于你想要为空，元素和属性中删除数据，然后将修改后的实例文件保存。</span><span class="sxs-lookup"><span data-stu-id="79644-107">Open the input instance message in a text editor, delete the data from elements and attributes that you want to be empty, and then save the modified instance file.</span></span>  

3. <span data-ttu-id="79644-108">配置 BizTalk 映射器以使用刚刚修改过的架构验证和测试的文件。</span><span class="sxs-lookup"><span data-stu-id="79644-108">Configure BizTalk Mapper to use the file you just modified when the schema is validated and tested.</span></span> <span data-ttu-id="79644-109">在为架构属性窗口中设置该文件。</span><span class="sxs-lookup"><span data-stu-id="79644-109">You set the file in the Properties window for the schema.</span></span> <span data-ttu-id="79644-110">有关设置属性的详细信息，请参阅**映射文件属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="79644-110">For more information about setting properties, see **Map File Properties** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="79644-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="79644-111">See Also</span></span>  
- [<span data-ttu-id="79644-112">如何生成实例消息</span><span class="sxs-lookup"><span data-stu-id="79644-112">How to Generate Instance Messages</span></span>](../core/how-to-generate-instance-messages.md)   
- <span data-ttu-id="79644-113">**架构属性参考** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="79644-113">**Schema Property Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
