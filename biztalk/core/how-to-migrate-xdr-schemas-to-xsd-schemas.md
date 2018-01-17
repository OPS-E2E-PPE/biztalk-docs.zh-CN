---
title: "如何将 XDR 架构迁移到 XSD 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90bde0d0-bfe6-4d6c-823c-8ed9c0e15783
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84bbc42297a10c7d42adb8d778ba19b3b392742c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-migrate-xdr-schemas-to-xsd-schemas"></a><span data-ttu-id="f6c46-102">如何将 XDR 架构迁移到 XSD 架构</span><span class="sxs-lookup"><span data-stu-id="f6c46-102">How to Migrate XDR Schemas to XSD Schemas</span></span>
<span data-ttu-id="f6c46-103">如果是从早期版本的 BizTalk Server 迁移架构，则需要将精简 XML 数据 (XDR) 架构转换为 XML 架构定义 (XSD) 语言架构。</span><span class="sxs-lookup"><span data-stu-id="f6c46-103">If you are migrating schemas from a previous version of BizTalk Server, you will need to convert your XML-Data Reduced (XDR) schemas into XML Schema definition (XSD) language schemas.</span></span> <span data-ttu-id="f6c46-104">本主题介绍了必需的步骤。</span><span class="sxs-lookup"><span data-stu-id="f6c46-104">This topic describes the necessary steps.</span></span>  
  
### <a name="to-generate-an-xsd-schema-from-an-xdr-schema"></a><span data-ttu-id="f6c46-105">从 XDR 架构生成 XSD 架构</span><span class="sxs-lookup"><span data-stu-id="f6c46-105">To generate an XSD schema from an XDR schema</span></span>  
  
1.  <span data-ttu-id="f6c46-106">在 **解决方案资源管理器**, ，右键单击相关的 BizTalk 项目，指向 **添加**, ，然后单击 **添加生成的项**。</span><span class="sxs-lookup"><span data-stu-id="f6c46-106">In **Solution Explorer**, right-click the relevant BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  
  
2.  <span data-ttu-id="f6c46-107">在**添加生成项- \< *BizTalk ProjectName* \>** 对话框中，在**模板**部分中，单击**生成架构**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="f6c46-107">In the **Add Generated Item - \<*BizTalk ProjectName*\>** dialog box, in the **Templates** section, click **Generate Schemas**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="f6c46-108">在 **生成架构** 对话框中，在 **文档类型** 列表中，选择 **XDR 架构**。</span><span class="sxs-lookup"><span data-stu-id="f6c46-108">In the **Generate Schemas** dialog box, in the **Document type** list, select **XDR Schema**.</span></span>  
  
4.  <span data-ttu-id="f6c46-109">单击 **浏览**, ，找到你想要迁移，并依次 XDR 架构文件 **确定**。</span><span class="sxs-lookup"><span data-stu-id="f6c46-109">Click **Browse**, locate the XDR schema file you want to migrate, and then click **OK**.</span></span>  
  
     <span data-ttu-id="f6c46-110">此时，将从指定的 XDR 架构文件生成与该文件同名并具有 .xsd 扩展名的新架构，然后在 BizTalk 编辑器中打开该架构。</span><span class="sxs-lookup"><span data-stu-id="f6c46-110">A new schema is generated from the specified XDR schema file, using the same name as that file with the .xsd extension, and then opened in BizTalk Editor.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6c46-111">不要使用 C# 保留字以及 .NET Framework 类型和命名空间名称（例如 System）作为架构根节点名称或文件名。</span><span class="sxs-lookup"><span data-stu-id="f6c46-111">Avoid using C# reserved words and .NET Framework type and namespace names (such as System) as schema root node names or as file names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6c46-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6c46-112">See Also</span></span>  
 <span data-ttu-id="f6c46-113">[管理架构在项目中](../core/managing-schemas-within-projects.md) </span><span class="sxs-lookup"><span data-stu-id="f6c46-113">[Managing Schemas Within Projects](../core/managing-schemas-within-projects.md) </span></span>  
 [<span data-ttu-id="f6c46-114">迁移平面文件记录</span><span class="sxs-lookup"><span data-stu-id="f6c46-114">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)