---
title: "正在验证适配器配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8eeb8742-7083-462b-8d3a-e58103112542
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 380aa4c78a6a24fd84edea2614f02a9fcd772dbb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validating-the-adapter-configuration"></a><span data-ttu-id="c9f80-102">正在验证适配器配置</span><span class="sxs-lookup"><span data-stu-id="c9f80-102">Validating the Adapter Configuration</span></span>
<span data-ttu-id="c9f80-103">时添加的接收位置和发送端口，你将需要配置在你自定义属性 **\<** *适配器名称***> 传输属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="c9f80-103">While adding the receive location and send port, you will be asked to configure your custom properties in the **\<***Adapter Name***> Transport Properties** dialog box.</span></span> <span data-ttu-id="c9f80-104">AdapterHarness 项目中的 XSD 架构文件用于定义这些属性。</span><span class="sxs-lookup"><span data-stu-id="c9f80-104">The XSD schema files in the AdapterHarness project define these properties.</span></span>  
  
 <span data-ttu-id="c9f80-105">架构配置的验证分三种情况：</span><span class="sxs-lookup"><span data-stu-id="c9f80-105">Validation of the configuration schema occurs in three parts:</span></span>  
  
1.  <span data-ttu-id="c9f80-106">显示保存的配置时，在将保存的 XML 文档加载到属性页之前，适配器框架会根据架构验证该文档。</span><span class="sxs-lookup"><span data-stu-id="c9f80-106">When displaying a saved configuration, the Adapter Framework validates the saved XML document against the schema before loading the document into the property page.</span></span> <span data-ttu-id="c9f80-107">该框架假定文档无效表示配置架构定义发生了更改。</span><span class="sxs-lookup"><span data-stu-id="c9f80-107">The framework assumes that a document that is not valid indicates a change in the configuration schema definition.</span></span> <span data-ttu-id="c9f80-108">只有有效的文档才能加载到属性页中。</span><span class="sxs-lookup"><span data-stu-id="c9f80-108">Only valid documents get loaded into the property page.</span></span>  
  
2.  <span data-ttu-id="c9f80-109">保存配置时，如果适配器实现时**IAdapterConfigValidation**接口，框架将传递给构造的 XML 文档的适配器从序列化的属性页数据。</span><span class="sxs-lookup"><span data-stu-id="c9f80-109">When saving a configuration, if the adapter implements the **IAdapterConfigValidation** interface, the framework passes to the adapter the XML document constructed from serializing the property page data.</span></span> <span data-ttu-id="c9f80-110">然后适配器处理该文档。</span><span class="sxs-lookup"><span data-stu-id="c9f80-110">The adapter then processes the document.</span></span> <span data-ttu-id="c9f80-111">出现任何错误都会产生异常，这些异常由框架捕获并显示给用户。</span><span class="sxs-lookup"><span data-stu-id="c9f80-111">Any errors should produce exceptions that are caught by the framework and displayed to the user.</span></span> <span data-ttu-id="c9f80-112">任何缺少的值或生成的值都会在验证过程中生成。</span><span class="sxs-lookup"><span data-stu-id="c9f80-112">Any missing or generated values should be generated during validation.</span></span> <span data-ttu-id="c9f80-113">使用\<可浏览显示 ="false"> 修饰取消显示一个条目，在属性网格中，即使值出现在 XML 实例。</span><span class="sxs-lookup"><span data-stu-id="c9f80-113">Using the \<browsable show="false"> decoration suppresses showing an entry in the property grid, even though the value appears in the XML instance.</span></span>  
  
3.  <span data-ttu-id="c9f80-114">保存配置以将值放入数据库时，框架将再次根据架构验证 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="c9f80-114">When saving a configuration before placing the value into the database, the framework again validates the XML document against the schema.</span></span> <span data-ttu-id="c9f80-115">这可确保只保存有效数据。</span><span class="sxs-lookup"><span data-stu-id="c9f80-115">This ensures that only valid data is persisted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9f80-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9f80-116">See Also</span></span>  
 [<span data-ttu-id="c9f80-117">适配器设计问题</span><span class="sxs-lookup"><span data-stu-id="c9f80-117">Adapter Design Issues</span></span>](../core/adapter-design-issues.md)