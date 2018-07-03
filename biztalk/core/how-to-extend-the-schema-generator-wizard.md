---
title: 如何扩展架构生成器向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- utilities, Schema Generator Wizard
- Schema Generator Wizard
ms.assetid: ea4b5532-f904-4da0-9612-e092e7e4edc1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6fb901186dddf69a94fca4467b543f047c27719
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013806"
---
# <a name="how-to-extend-the-schema-generator-wizard"></a><span data-ttu-id="b7ca6-102">如何扩展架构生成器向导</span><span class="sxs-lookup"><span data-stu-id="b7ca6-102">How to Extend the Schema Generator Wizard</span></span>
<span data-ttu-id="b7ca6-103">如何扩展现有架构生成器向导以及如何为架构生成创建一个新的向导。</span><span class="sxs-lookup"><span data-stu-id="b7ca6-103">How to extend the existing Schema Generator Wizard and how to create a new wizard for schema generation.</span></span>  
  
## <a name="extend-the-existing-schema-wizard"></a><span data-ttu-id="b7ca6-104">扩展现有架构向导</span><span class="sxs-lookup"><span data-stu-id="b7ca6-104">Extend the existing schema wizard</span></span>  
  
1. <span data-ttu-id="b7ca6-105">实现 ISchemaGenerator 接口，以创建可以集成到现有架构生成器向导中的新架构生成器模块。</span><span class="sxs-lookup"><span data-stu-id="b7ca6-105">Implement the ISchemaGenerator interface to create a new schema generator module that you can integrate into the existing Schema Generator Wizard.</span></span>  
  
   ```  
   public interface ISchemaGenerator  
   {  
   //Method to extract a schema from a document.  
   void GenerateSchema(string inputDocument,string outputDocumentPath);  
  
   //Method to extract the errors.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] Errors();  
  
   //Method to extract the warnings.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] Warnings();  
  
   //Method to extract the referenced schemas.  
   [return : MarshalAs(UnmanagedType.SafeArray, SafeArraySubType = VarEnum.VT_VARIANT )]object [] ReferencedSchemas();  
   }  
   ```  
  
2. <span data-ttu-id="b7ca6-106">将生成的程序集放入以下 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装文件夹中：</span><span class="sxs-lookup"><span data-stu-id="b7ca6-106">Drop the resulting assembly in the following Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation folder:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b7ca6-107">\Developer Tools\Schema 编辑器扩展</span><span class="sxs-lookup"><span data-stu-id="b7ca6-107">\Developer Tools\Schema Editor Extensions</span></span>  
  
    <span data-ttu-id="b7ca6-108">下次运行架构生成器向导时，此向导将自动加载新的架构生成器模块。</span><span class="sxs-lookup"><span data-stu-id="b7ca6-108">The next time you run the Schema Generator Wizard, it will automatically pick up your new schema generator module.</span></span>  
  
   <span data-ttu-id="b7ca6-109">可使用以下过程创建新架构向导。</span><span class="sxs-lookup"><span data-stu-id="b7ca6-109">Use the following procedure to create a new schema wizard.</span></span>  
  
   <span data-ttu-id="b7ca6-110">**在 SDK 中的位置**</span><span class="sxs-lookup"><span data-stu-id="b7ca6-110">**Location in SDK**</span></span>  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="b7ca6-111">\SDK\Utilities\Schema generator</span><span class="sxs-lookup"><span data-stu-id="b7ca6-111">\SDK\Utilities\Schema Generator</span></span>  
  
### <a name="create-a-new-schema-wizard"></a><span data-ttu-id="b7ca6-112">创建新架构向导</span><span class="sxs-lookup"><span data-stu-id="b7ca6-112">Create a new schema wizard</span></span>  
  
1. <span data-ttu-id="b7ca6-113">运行 InstallDTD.vbs 以将 Microsoft.BizTalk.DTDToXSDGenerator.dll 安装到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展。</span><span class="sxs-lookup"><span data-stu-id="b7ca6-113">Run InstallDTD.vbs to install Microsoft.BizTalk.DTDToXSDGenerator.dll to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema Editor Extensions.</span></span> <span data-ttu-id="b7ca6-114">DTDToXSDGenerator.dll 公开了可用于将 DTD 文件转换为 XSD 的类。</span><span class="sxs-lookup"><span data-stu-id="b7ca6-114">DTDToXSDGenerator.dll exposes classes you can use to convert DTD files to XSD.</span></span>  
  
2. <span data-ttu-id="b7ca6-115">运行 InstallWFX.vbs 以将 Microsoft.BizTalk.WFXToXSDGenerator.dll 安装到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展。</span><span class="sxs-lookup"><span data-stu-id="b7ca6-115">Run InstallWFX.vbs to install Microsoft.BizTalk.WFXToXSDGenerator.dll to [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema Editor Extensions.</span></span> <span data-ttu-id="b7ca6-116">WFXToXSDGenerator.dll 公开了可用于将 WFX 文件转换为 XSD 的类。</span><span class="sxs-lookup"><span data-stu-id="b7ca6-116">WFXToXSDGenerator.dll exposes classes you can use to convert WFX files to XSD.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ca6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b7ca6-117">See Also</span></span>  
 [<span data-ttu-id="b7ca6-118">SDK 中的实用工具</span><span class="sxs-lookup"><span data-stu-id="b7ca6-118">Utilities in the SDK</span></span>](../core/utilities-in-the-sdk.md)