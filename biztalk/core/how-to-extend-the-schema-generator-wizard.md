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
# <a name="how-to-extend-the-schema-generator-wizard"></a>如何扩展架构生成器向导
如何扩展现有架构生成器向导以及如何为架构生成创建一个新的向导。  
  
## <a name="extend-the-existing-schema-wizard"></a>扩展现有架构向导  
  
1. 实现 ISchemaGenerator 接口，以创建可以集成到现有架构生成器向导中的新架构生成器模块。  
  
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
  
2. 将生成的程序集放入以下 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装文件夹中：  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展  
  
    下次运行架构生成器向导时，此向导将自动加载新的架构生成器模块。  
  
   可使用以下过程创建新架构向导。  
  
   **在 SDK 中的位置**  
  
   [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\Utilities\Schema generator  
  
### <a name="create-a-new-schema-wizard"></a>创建新架构向导  
  
1. 运行 InstallDTD.vbs 以将 Microsoft.BizTalk.DTDToXSDGenerator.dll 安装到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展。 DTDToXSDGenerator.dll 公开了可用于将 DTD 文件转换为 XSD 的类。  
  
2. 运行 InstallWFX.vbs 以将 Microsoft.BizTalk.WFXToXSDGenerator.dll 安装到[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展。 WFXToXSDGenerator.dll 公开了可用于将 WFX 文件转换为 XSD 的类。  
  
## <a name="see-also"></a>请参阅  
 [SDK 中的实用工具](../core/utilities-in-the-sdk.md)