---
title: 第 2 步：创建和部署示例 X12 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5862168-6621-40ab-8c97-3f317530d34e
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a99083a5b0d4cc416f611e94ac35039921c8deba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392767"
---
# <a name="step-2-create-and-deploy-the-sample-x12-schema"></a>第 2 步：创建和部署示例 X12 架构
![步骤 2 时 11](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")  
  
 在此步骤中，将生成和部署提供了一个示例 EDI X 12 是通过 AS2 传输的过程的传入 EDI X 12 交换所需的架构的项目。 对于本教程，该架构为 X12_00401_864.xsd。 不需要更改项目随 AS2 教程;只需生成它。  
  
> [!NOTE]
>  在文件夹中存储的架构文件 X12_00401_864.xsd 本教程使用[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas。 它已添加到架构项目将生成和部署在此步骤。 此架构是通过执行文件夹中的 MicrosoftEdiXsdTemplates.exe 下载到您的计算机上的 X12_00401_864.xsd 文件不同[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI。 如果使用已添加到 Schemas.btproj 的 X12_00401_864.xsd 文件，本教程才有效。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。  
  
### <a name="to-create-and-deploy-the-sample-x12-schema"></a>若要创建和部署示例 X12 架构  
  
1. 启动**Microsoft Visual Studio**以管理员身份。  
  
2. 在中[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，打开解决方案[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.sln。  
  
   > [!NOTE]
   >  本主题假定你已从对 BizTalk EDI 应用程序，其中包含 EDI 架构、 管道和业务流程应用程序中添加了一个引用。 如果没有，请参阅[如何添加对 BizTalk Server EDI 应用程序的引用](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)。  
  
3. 右键单击架构项目中，然后依次**属性**。 单击**签名**项目设计器中的选项卡。 检查**为程序集签名**复选框，为**选择一个强密钥名称的文件**，选择**\<新建...\>** 并输入`Schemas.snk`。 清除**保护密钥文件使用密码**，然后单击**确定**。 关闭项目属性对话框并保存所做的更改。  
  
4. 生成并部署 Schemas.btproj。  
  
## <a name="next-steps"></a>后续步骤  
 配置参与方和业务配置文件为你的组织 (Contoso)，如中所述[步骤 3:为你的组织配置参与方和业务配置文件](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)。  
  
## <a name="see-also"></a>请参阅  
 [EDI 文档架构](../core/edi-document-schemas.md)