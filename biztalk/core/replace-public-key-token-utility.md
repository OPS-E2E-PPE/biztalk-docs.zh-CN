---
title: 替换公钥令牌实用工具 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Replace Public Key Token Utility
- utilities, Replace Public Key Token Utility
- public key token
ms.assetid: ed8673b9-af06-4bd7-b8b7-7371e4dd0fed
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5754f9ee853f1501d247f1236ca89d158b3788c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397900"
---
# <a name="replace-public-key-token-utility"></a>替换公钥令牌实用工具
此实用程序可用于从强名称程序集密钥 (.snk) 文件派生公钥标记替换的公钥标记或变量的文件中。  
  
 开发人员编写使用的脚本时，此实用程序可能很有用[BTSTask 命令行参考](../core/btstask-command-line-reference.md)部署的程序集。 有关部署成功完成，程序集的完全限定的名称必须提供，其中包括其公钥标记。 程序集的公钥标记是从.snk 文件中提取并在生成时分配给该程序集。 该程序集部署到新的环境之前，但是，它是通常使用重新生成其他公钥标记。 因此，开发人员可能不知道部署脚本运行时将程序集使用什么公钥标记。  
  
 有两种方法，可以使用替换公钥标记实用程序来处理这种情况：  
  
-   **方案 1。** 在部署脚本中，开发人员可以使用公钥标记或占位符表示公钥标记。 之前运行脚本后，用户可以运行替换公钥标记实用程序从.snk 文件用于生成的程序集的目标环境中提取公钥标记替换公钥标记或脚本文件中的占位符。  
  
-   **方案 2。** 开发人员可以配置为自动替代新公钥标记，按如下所示的脚本：在脚本开始时，调用替换公钥标记实用程序和指向包含公钥标记的.snk 文件。 在脚本中，使用环境变量 %NEWTOKEN%表示公钥标记。 当脚本运行时，该实用程序从.snk 文件中提取公钥标记的值，并将其设置到环境变量 %NEWTOKEN%。 当脚本运行时，%NEWTOKEN%的每个实例将用指定的.snk 文件中的公钥标记。 例如：  
  
    ```  
    ReplacePKT.bat key.snk  
    ...  
    ...  
    gacutil /u Assembly, ... PublicKey=%NEWTOKEN% ...  
    ```  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 替换公钥标记实用程序位于：  
  
 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Utilities\ReplacePublicKeyToken\\。  
  
 替换公钥标记实用程序包括三个文件：  
  
-   ReplacePKT.bat  
  
-   ReplacePKT.vbs  
  
-   ReplacePKT.wsf  
  
## <a name="procedures"></a>过程  
 使用以下过程在方案 1 中所述，使用从.snk 文件中提取公钥标记替换公钥标记或占位符文件中的所有实例。  
  
#### <a name="to-replace-instances-of-a-public-key-token-or-a-placeholder-in-a-file"></a>替换公钥标记或占位符文件中的实例  
  
1. 请确保三个替换公钥标记实用程序文件 （ReplacePKT.bat、 ReplacePKT.vbs、 ReplacePKT.wsf）、 脚本文件和.snk 文件可从本地计算机。  
  
2. 在命令窗口中，将目录更改到包含替换公钥标记实用程序文件的文件夹中。  
  
3. 从命令提示符处，运行以下命令：  
  
4. **ReplacePKT \<**  *.snk 文件* **\> \<** *旧公钥标记* **\>\<** *文件替换* **\>**  
  
   |Option|Description|  
   |------------|-----------------|  
   |**\<** *.snk 文件* **\>**|包含所需的公钥标记的.snk 文件的完整路径替换现有的公钥标记或占位符。|  
   |**\<** *旧公钥标记* **\>**|公钥标记或您要替换的占位符。|  
   |**\<** *若要替换的文件* **\>**|想要替换的公钥标记或占位符的文件的完整路径。|  
  
    例如：  
  
    **ReplacePKT.bat C:\Tokens\MyToken.snk 12ab3456cd789e12 C:\Scripts\MyScript.vbs**  
  
   使用以下过程中使用从.snk 文件派生的公钥标记，如方案 2 中所述的脚本自动设置环境变量。  
  
#### <a name="to-set-an-environment-variable-that-uses-a-public-key-token"></a>若要设置使用公钥标记的环境变量  
  
1.  在脚本文件的开头，添加以下代码行：  
  
    ```  
    ReplacePKT <filename>.snk  
    ```  
  
     其中\<*文件名*\>是从中派生公钥标记的.snk 文件的名称。  
  
    ```  
    Example: ReplacePKT.bat MyToken.snk  
    ```  
  
2.  在脚本文件中，使用`%NEWTOKEN%`来表示公钥标记。  
  
     例如：  
  
    ```  
    PublicKey=%NEWTOKEN%  
    ```  
  
3.  当向用户提供脚本文件时，包括组成替换公钥标记实用程序 （ReplacePKT.bat、 ReplacePKT.vbs、 ReplacePKT.wsf） 的三个文件。 请确保，您的脚本的用户的所有文件之前复制到文件系统上的相同文件夹运行您的脚本。  
  
## <a name="see-also"></a>请参阅  
 [SDK 中的实用工具](../core/utilities-in-the-sdk.md)