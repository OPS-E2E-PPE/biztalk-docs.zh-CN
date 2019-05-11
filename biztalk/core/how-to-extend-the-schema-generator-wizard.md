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
ms.openlocfilehash: 6ac920751fc8f653433525150be5684f93d2eb2b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337710"
---
# <a name="how-to-extend-the-schema-generator-wizard"></a>如何扩展架构生成器向导
如何扩展现有架构生成器向导以及如何为架构生成创建一个新的向导。  
  
## <a name="extend-the-existing-schema-wizard"></a>扩展现有架构向导  
  
1. 实现 ISchemaGenerator 接口，以创建新的架构生成器模块，您可以将它们集成到现有架构生成器向导。  
  
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
  
2. 生成的程序集放入以下 microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装文件夹：  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展  
  
    在下次运行架构生成器向导，它会自动选取新的架构生成器模块。  
  
   使用以下过程创建新架构向导。  
  
   **在 SDK 中的位置**  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\Utilities\Schema Generator  
  
### <a name="create-a-new-schema-wizard"></a>创建新架构向导  
  
1. 运行 InstallDTD.vbs 以将 Microsoft.BizTalk.DTDToXSDGenerator.dll 安装到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展。 DTDToXSDGenerator.dll 公开了可用于将 DTD 文件转换为 XSD 的类。  
  
2. 运行 InstallWFX.vbs 以将 Microsoft.BizTalk.WFXToXSDGenerator.dll 安装到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展。 WFXToXSDGenerator.dll 公开了可用于将 WFX 文件转换为 XSD 的类。  
  
## <a name="see-also"></a>请参阅  
 [SDK 中的实用工具](../core/utilities-in-the-sdk.md)