---
title: "步骤 2： 创建并部署示例 X12 架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5862168-6621-40ab-8c97-3f317530d34e
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe4f937af910ceef1ed461e25ea3c62cad5cbc29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-and-deploy-the-sample-x12-schema"></a>步骤 2： 创建并部署示例 X12 架构
![步骤 2，共 11](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")  
  
 在本步骤中，你将生成和部署提供一个示例 EDI X12 架构的项目，该架构是处理通过 AS2 传输的传入 EDI X12 交换所必需的。 对于本教程，该架构为 X12_00401_864.xsd。 无需更改 AS2 教程附带的项目，只需对它执行生成操作即可。  
  
> [!NOTE]
>  本教程使用的架构文件 X12_00401_864.xsd 存储在文件夹 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\AS2 Tutorial\Schemas 中。 它已经添加到你要在本步骤中生成和部署的“架构”项目中。 此架构与通过执行文件夹 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 中的 MicrosoftEdiXsdTemplates.exe 下载到你计算机上的 X12_00401_864.xsd 文件不同。 仅当使用已添加到 Schemas.btproj 的 X12_00401_864.xsd 文件时，本教程才适用。  
  
## <a name="prerequisites"></a>先决条件  
 你必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组成员的身份登录。  
  
### <a name="to-create-and-deploy-the-sample-x12-schema"></a>创建和部署示例 X12 架构  
  
1.  启动**Microsoft Visual Studio**以管理员身份。  
  
2.  在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中，打开解决方案 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)] SDK\AS2 Tutorial\Schemas\Schemas.sln。  
  
    > [!NOTE]
    >  本主题假定你已从你的应用程序添加了对包含 EDI 架构、管道和业务流程的 BizTalk EDI 应用程序的引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
3.  右键单击架构项目中，并依次**属性**。 单击**签名**项目设计器中的选项卡。 检查**对程序集签名**复选框，为**选择强密钥名称文件**，选择**\<新建 … >**并输入`Schemas.snk`。 清除**保护我使用密码的密钥文件**，然后单击**确定**。 关闭项目属性对话框并保存所做的更改。  
  
4.  生成并部署 Schemas.btproj。  
  
## <a name="next-steps"></a>后续步骤  
 配置当事方和业务配置文件为你的组织 (Contoso) 中所述[步骤 3： 将方和业务配置文件配置为你的组织](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)。  
  
## <a name="see-also"></a>另请参阅  
 [EDI 文档架构](../core/edi-document-schemas.md)