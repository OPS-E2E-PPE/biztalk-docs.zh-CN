---
title: 如何扩展架构生成器向导 |Microsoft 文档
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
ms.openlocfilehash: 11db44e07191b0996043dd6b819ef2ba9162a0e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254013"
---
# <a name="how-to-extend-the-schema-generator-wizard"></a>如何扩展架构生成器向导
如何扩展现有的架构生成器向导以及如何为架构生成创建新的向导。  
  
## <a name="extend-the-existing-schema-wizard"></a>扩展现有的架构向导  
  
1.  实现 ISchemaGenerator 接口，以创建可以集成到现有架构生成器向导中的新架构生成器模块。  
  
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
  
2.  将生成的程序集放入以下 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装文件夹中：  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展  
  
     下次运行架构生成器向导时，此向导将自动加载新的架构生成器模块。  
  
 可使用以下过程创建新架构向导。  
  
 **SDK 中的位置**  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\SDK\Utilities\Schema 生成器  
  
### <a name="create-a-new-schema-wizard"></a>创建新的架构向导  
  
1.  运行 InstallDTD.vbs 安装到 Microsoft.BizTalk.DTDToXSDGenerator.dll [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展。 DTDToXSDGenerator.dll 公开了可用于将 DTD 文件转换为 XSD 的类。  
  
2.  运行 InstallWFX.vbs 安装到 Microsoft.BizTalk.WFXToXSDGenerator.dll [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]\Developer Tools\Schema 编辑器扩展。 WFXToXSDGenerator.dll 公开了可用于将 WFX 文件转换为 XSD 的类。  
  
## <a name="see-also"></a>另请参阅  
 [SDK 中的实用程序](../core/utilities-in-the-sdk.md)