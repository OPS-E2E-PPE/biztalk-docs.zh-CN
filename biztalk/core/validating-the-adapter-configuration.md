---
title: 正在验证适配器配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8eeb8742-7083-462b-8d3a-e58103112542
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc36a885614eac72f70e588fefe4731717322019
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279550"
---
# <a name="validating-the-adapter-configuration"></a><span data-ttu-id="80c6b-102">正在验证适配器配置</span><span class="sxs-lookup"><span data-stu-id="80c6b-102">Validating the Adapter Configuration</span></span>
<span data-ttu-id="80c6b-103">同时添加接收位置和发送端口，您将需要配置自定义属性中的**\<**<em>适配器名称</em> **\>传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="80c6b-103">While adding the receive location and send port, you will be asked to configure your custom properties in the **\<**<em>Adapter Name</em>**\> Transport Properties** dialog box.</span></span> <span data-ttu-id="80c6b-104">AdapterHarness 项目中的 XSD 架构文件定义这些属性。</span><span class="sxs-lookup"><span data-stu-id="80c6b-104">The XSD schema files in the AdapterHarness project define these properties.</span></span>  
  
 <span data-ttu-id="80c6b-105">配置架构验证发生在三个部分：</span><span class="sxs-lookup"><span data-stu-id="80c6b-105">Validation of the configuration schema occurs in three parts:</span></span>  
  
1.  <span data-ttu-id="80c6b-106">在显示时保存的配置，适配器框架将文档加载到属性页之前会验证针对该架构保存的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="80c6b-106">When displaying a saved configuration, the Adapter Framework validates the saved XML document against the schema before loading the document into the property page.</span></span> <span data-ttu-id="80c6b-107">框架将假定不是有效的文档指示配置架构定义中的更改。</span><span class="sxs-lookup"><span data-stu-id="80c6b-107">The framework assumes that a document that is not valid indicates a change in the configuration schema definition.</span></span> <span data-ttu-id="80c6b-108">只有有效的文档加载到属性页。</span><span class="sxs-lookup"><span data-stu-id="80c6b-108">Only valid documents get loaded into the property page.</span></span>  
  
2.  <span data-ttu-id="80c6b-109">保存配置，如果适配器实现时**IAdapterConfigValidation**接口，该框架传递到适配器构造的 XML 文档序列化属性页数据。</span><span class="sxs-lookup"><span data-stu-id="80c6b-109">When saving a configuration, if the adapter implements the **IAdapterConfigValidation** interface, the framework passes to the adapter the XML document constructed from serializing the property page data.</span></span> <span data-ttu-id="80c6b-110">然后，适配器处理文档。</span><span class="sxs-lookup"><span data-stu-id="80c6b-110">The adapter then processes the document.</span></span> <span data-ttu-id="80c6b-111">任何错误应生成的异常由框架捕获并向用户显示。</span><span class="sxs-lookup"><span data-stu-id="80c6b-111">Any errors should produce exceptions that are caught by the framework and displayed to the user.</span></span> <span data-ttu-id="80c6b-112">应在验证过程中生成任何缺失或生成值。</span><span class="sxs-lookup"><span data-stu-id="80c6b-112">Any missing or generated values should be generated during validation.</span></span> <span data-ttu-id="80c6b-113">使用\<可浏览 show ="false"\>修饰可取消其中一个条目显示在属性网格中，即使此值出现在 XML 实例。</span><span class="sxs-lookup"><span data-stu-id="80c6b-113">Using the \<browsable show="false"\> decoration suppresses showing an entry in the property grid, even though the value appears in the XML instance.</span></span>  
  
3.  <span data-ttu-id="80c6b-114">在保存之前将值放入数据库的配置时，框架将再次验证针对该架构的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="80c6b-114">When saving a configuration before placing the value into the database, the framework again validates the XML document against the schema.</span></span> <span data-ttu-id="80c6b-115">这可确保仅有效的数据将保留。</span><span class="sxs-lookup"><span data-stu-id="80c6b-115">This ensures that only valid data is persisted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c6b-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="80c6b-116">See Also</span></span>  
 [<span data-ttu-id="80c6b-117">适配器设计问题</span><span class="sxs-lookup"><span data-stu-id="80c6b-117">Adapter Design Issues</span></span>](../core/adapter-design-issues.md)