---
title: 步骤 4：创建 HeaderHelper 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- projects, helper projects
- private process tutorial, creating helper projects
ms.assetid: 82413537-032a-4368-8d77-d024a7c83b0b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 850c3b5321c5b167bf3946a26d94db21bdb6ba35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280917"
---
# <a name="step-4-creating-the-headerhelper-project"></a>步骤 4：创建 HeaderHelper 项目
在此步骤中，您将创建[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]类库。 当专用业务流程收到传入消息时，HeaderHelper 库确定的文档转换是否是必需的如果它是必需的则执行该转换。 这使您的业务流程处理 RosettaNet 实现框架 (RNIF) 文档的不同版本。 此外，3A2 响应消息发送时，HeaderHelper 库在执行传送该消息之前的其他文档转换。  
  
### <a name="to-create-the-headerhelper-project"></a>若要创建 HeaderHelper 项目  
  
1. 在中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器中右键单击 Contoso 解决方案，指向**添加**，然后单击**新项目**。  
  
2. 在添加新项目对话框中，在项目类型窗格中，选择**Visual C#**。  
  
3. 在模板窗格中选择**类库**模板。  
  
4. 在中**名称**框中，键入**HeaderHelper**，然后单击**确定**创建项目。  
  
5. 在解决方案资源管理器，右键单击**Class1.cs**中的文件**HeaderHelper**项目，然后单击**重命名**，类型**HeaderHelper.cs**，然后按**Enter**。  
  
### <a name="to-create-the-helper-class"></a>若要创建帮助器类  
  
1.  在解决方案资源管理器，展开**HeaderHelper**项目，然后再双击**HeaderHelper.cs**节点以打开 HeaderHelper 源文件。  
  
2.  键入以下代码到源文件，覆盖所有现有代码：  
  
    ```  
    using System;  
    using System.Xml;  
  
    namespace ContosoPriceAndAvailability  
    {  
        public class Helper  
        {  
            static public XmlDocument NormalizeHeader( XmlDocument curPip )  
            {  
                string strInput = curPip.OuterXml;  
                try  
                {  
                    XmlDocument xDoc = new XmlDocument();  
  
                    strInput = strInput.Replace("<!DOCTYPE Pip3A2PriceAndAvailabilityQuery SYSTEM \"3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\"[]>",String.Empty);  
                    strInput = strInput.Replace("<Pip3A2PriceAndAvailabilityQuery>","<Pip3A2PriceAndAvailabilityQuery xmlns=\"http://schemas.microsoft.com/biztalk/btarn/2004/3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd\">");  
                    strInput = strInput.Replace("xml:",String.Empty);  
                    strInput = strInput.Replace("b:",String.Empty);  
                    strInput = strInput.Replace("lang:",String.Empty);  
                    strInput = strInput.Replace("ns1:",String.Empty);  
  
                    xDoc.LoadXml(strInput);  
  
                    return xDoc;  
                }  
                catch(Exception ex)  
                {  
                    System.Diagnostics.Debug.Write( ex.Message );  
                    throw ex;  
                }  
            }  
  
            static public string ReturnSCWithDocType( XmlDocument xmlDoc )  
            {  
                try  
                {  
                    string sResponse = xmlDoc.InnerXml;  
                    sResponse=sResponse.Replace("ns0:",String.Empty);  
                    xmlDoc.LoadXml(sResponse);  
                    xmlDoc.DocumentElement.RemoveAllAttributes();  
                    sResponse = xmlDoc.InnerXml;  
  
                    sResponse = sResponse.Insert(0,"<!DOCTYPE Pip3A2PriceAndAvailabilityResponse SYSTEM \"3A2PriceAndAvailabilityResponseMessageGuideline_v1_3.dtd\">");  
                    sResponse = sResponse.Replace("ns0:",String.Empty);  
                    sResponse = sResponse.Replace("b:",String.Empty);  
                    sResponse = sResponse.Replace("lang:",String.Empty);  
                    sResponse = sResponse.Replace("ns1:",String.Empty);  
  
                    return sResponse;  
                }  
                catch(Exception ex)  
                {  
                    throw ex;  
                }  
            }  
        }  
    }  
    ```  
  
3.  在“文件”  菜单上，单击“全部保存” 。  
  
### <a name="to-create-a-strong-named-assembly-for-the-headerhelper-project"></a>若要创建 HeaderHelper 项目的强命名程序集  
  
1.  在解决方案资源管理器中右键单击**HeaderHelper**项目，并单击**属性**。  
  
2.  在 HeaderHelper 属性页对话框中，选择**签名**HeaderHelp 属性窗格的左窗格中。  
  
3.  在右窗格中，单击**为程序集签名**。  
  
4.  单击**选择强名称密钥文件**文本框中，并选择**\<浏览\>** 从下拉列表。  
  
5.  在选择文件对话框中，转到 Contoso 程序集的位置，然后双击**FabConPriceAvail.snk**。  
  
6.  在“文件”  菜单上，单击“全部保存” 。  
  
7.  在解决方案资源管理器，展开**HeaderHelper**项目中，展开**属性**节点，然后再双击**AssemblyInfo.cs**节点打开 AssemblyInfo.cs源文件。  
  
8.  在 AssemblyInfo.cs 源文件中，键入以下代码行上的 AssemblyCulture 属性后面：  
  
    ```  
    [assembly: AssemblyKeyFile("../../../FabConPriceAvail.snk")]  
    ```  
  
9. 在“文件”  菜单上，单击“全部保存” 。  
  
### <a name="to-build-and-deploy-the-headerhelper-project"></a>若要生成和部署 HeaderHelper 项目  
  
1.  在解决方案资源管理器中右键单击**HeaderHelper**项目，并单击**生成**。  
  
2.  启动**Visual Studio 2012 命令提示符**。  
  
3.  在命令提示符下，将移动到的位置**HeaderHelper**项目输出目录 （\Bin\Debug 文件夹）。  
  
4.  在命令提示符处，键入**gacutil /if HeaderHelper.dll**然后按**Enter**安装**HeaderHelper**程序集到**全局程序集缓存**.  
  
## <a name="see-also"></a>请参阅  
 [步骤 5：修改 Contoso 专用业务流程](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md)