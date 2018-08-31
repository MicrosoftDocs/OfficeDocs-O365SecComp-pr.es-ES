---
title: Probar análisis de relevancia en eDiscovery avanzado de Office 365
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 9/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 1b092f7c-ea55-44f5-b419-63f3458fd7e0
description: 'Obtenga información sobre cómo usar la pestaña prueba después del cálculo de lote en Office 365 avanzada exhibición de documentos electrónicos para probar, comparar y validar la calidad total de procesamiento.  '
ms.openlocfilehash: 782859fe3b6bb3d00945c477928131cd1154446d
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2018
ms.locfileid: "22536215"
---
# <a name="test-relevance-analysis-in-office-365-advanced-ediscovery"></a><span data-ttu-id="56fce-103">Probar análisis de relevancia en eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="56fce-103">Test Relevance analysis in Office 365 Advanced eDiscovery</span></span>

> [!NOTE]
> <span data-ttu-id="56fce-p101">Exhibición de documentos electrónicos avanzada requiere un E3 de Office 365 con el complemento de cumplimiento avanzadas o una suscripción E5 para su organización. Si no tiene ese plan y desea probar avanzada exhibición de documentos electrónicos, puede [registrarse y obtener una versión de prueba de Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span><span class="sxs-lookup"><span data-stu-id="56fce-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="56fce-p102">La ficha de prueba de exhibición de documentos electrónicos avanzada permite probar, comparar y validar la calidad total de procesamiento. Estas pruebas se llevan a cabo después del cálculo por lotes. Al etiquetar los archivos en la colección, con un experto hace que la sentencia firme sobre si es realmente relevante para el caso de cada archivo con etiqueta.</span><span class="sxs-lookup"><span data-stu-id="56fce-p102">The Test tab in Advanced eDiscovery enables you to test, compare, and validate the overall quality of processing. These tests are performed after Batch calculation. By tagging the files in the collection, an expert makes the final judgment about whether each tagged file is actually relevant to the case.</span></span> 
  
<span data-ttu-id="56fce-p103">En los escenarios único y de varios problemas, normalmente se realizan pruebas por el problema. Los resultados se pueden ver después de cada prueba, y pueden ser se han rediseñado los resultados de la prueba con los archivos de prueba de ejemplo especificado.</span><span class="sxs-lookup"><span data-stu-id="56fce-p103">In single and multiple-issue scenarios, tests are typically performed per issue. Results can be viewed after each test, and test results can be reworked with specified sample test files.</span></span>
  
## <a name="testing-the-rest"></a><span data-ttu-id="56fce-111">Probar el resto</span><span class="sxs-lookup"><span data-stu-id="56fce-111">Testing the rest</span></span>

<span data-ttu-id="56fce-p104">La prueba de "Probar el resto" se usa para validar las decisiones de selección, por ejemplo, para revisar sólo archivos por encima de una puntuación del límite de la relevancia específico en función de los resultados de la exhibición de documentos electrónicos avanzada final. El experto revisa un ejemplo de los archivos en una puntuación de corte seleccionado para evaluar el número de archivos relevantes dentro de ese conjunto.</span><span class="sxs-lookup"><span data-stu-id="56fce-p104">The "Test the Rest" test is used to validate culling decisions, for example, to review only files above a specific Relevance cutoff score based on the final Advanced eDiscovery results. The expert reviews a sample of files under a selected cutoff score to evaluate the number of relevant files within that set.</span></span>
  
<span data-ttu-id="56fce-p105">Esta prueba proporciona estadísticas y una comparación entre el conjunto de revisión y la prueba de la población de Rest. Los resultados del conjunto de revisión son aquellos calcula la relevancia durante la formación. Los resultados incluyen los cálculos, en función de configuración y los parámetros de entrada, tales como:</span><span class="sxs-lookup"><span data-stu-id="56fce-p105">This test provides statistics and a comparison between the Review set and the Test the Rest population. The results of the review set are those calculated by Relevance during Training. The results include calculations , based on settings and input parameters, such as:</span></span>
  
- <span data-ttu-id="56fce-117">Probar las estadísticas de ejemplo del número de archivos en una muestra e identificados archivos relevantes.</span><span class="sxs-lookup"><span data-stu-id="56fce-117">Test sample statistics of the number of files in a sample and identified relevant files.</span></span> 
    
- <span data-ttu-id="56fce-p106">Comparación tabular de los parámetros de la población del conjunto de revisión y el resto, por ejemplo, el número de archivos, número estimado de archivos relevantes, estimado flexibilidad y el costo medio de buscar un archivo adicional relevante. Configuración de los parámetros de costos se puede establecer por el administrador.</span><span class="sxs-lookup"><span data-stu-id="56fce-p106">Tabular comparison of the Population parameters of the Review set and the Rest, for example, the number of files, estimated number of relevant files, estimated richness, and the average cost of finding an additional relevant file. Cost parameter settings can be set by the administrator.</span></span>
    
1. <span data-ttu-id="56fce-120">Abrir la **la relevancia \> prueba** ficha.</span><span class="sxs-lookup"><span data-stu-id="56fce-120">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="56fce-p107">En la ficha **probar** , haga clic en **probar de nuevo**. Se muestra el cuadro de diálogo **crear pruebas** , tal como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="56fce-p107">In the **Test** tab, click **New test**. The **Create test** dialog is displayed, as shown in the following example.</span></span> 
    
    ![Resultados de Probar el resto de relevancia](media/46e6898a-f929-4fd0-88d9-6f91d04b6ce2.png)
  
3. <span data-ttu-id="56fce-124">En **nombre de la prueba**y **Descripción**, escriba el nombre y la descripción.</span><span class="sxs-lookup"><span data-stu-id="56fce-124">In **Test name**, and **Description**, type the name and description.</span></span>
    
4. <span data-ttu-id="56fce-125">En la lista **tipo de prueba** , seleccione **el resto de la prueba**</span><span class="sxs-lookup"><span data-stu-id="56fce-125">In the **Test type** list, select **Test the Rest**</span></span>
    
5. <span data-ttu-id="56fce-126">En la **problema / categoría** de lista, seleccione el nombre del problema.</span><span class="sxs-lookup"><span data-stu-id="56fce-126">In the **Issue / Category** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="56fce-127">En la lista **de carga** , seleccione la carga.</span><span class="sxs-lookup"><span data-stu-id="56fce-127">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="56fce-128">En **% lectura**, acepte el valor predeterminado o seleccione un valor para la puntuación de relevancia el límite.</span><span class="sxs-lookup"><span data-stu-id="56fce-128">In **Read %**, accept the default value or select a value for the cutoff Relevance score.</span></span> 
    
8. <span data-ttu-id="56fce-p108">En **establecer tamaño**, o acepte el valor predeterminado. Tenga en cuenta que los iconos de restauración restaurará los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="56fce-p108">In **Set size**, or accept the default value. Note that the restore icons will restore the default values.</span></span>
    
9. <span data-ttu-id="56fce-p109">Haga clic en **Iniciar etiquetado**. Se genera una muestra de prueba.</span><span class="sxs-lookup"><span data-stu-id="56fce-p109">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="56fce-133">Revisar y marcar cada uno de los archivos en el **la relevancia \> etiqueta** ficha y cuando haya terminado, haga clic en **calcular**.</span><span class="sxs-lookup"><span data-stu-id="56fce-133">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span>
    
11. <span data-ttu-id="56fce-p110">En la ficha de prueba, puede hacer clic en **los resultados de la vista** para ver los resultados de pruebas. En la ilustración siguiente se muestra un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="56fce-p110">In the Test tab, you can click **View results** to see the test results. An example is shown in the following figure.</span></span> 
    
    ![Resultados de Probar el resto](media/b95744a9-047d-4c29-992d-04fa7e58e58a.png)
  
<span data-ttu-id="56fce-137">En la figura anterior, la sección **parámetros de ejemplo** de la tabla contiene detalles sobre el número de archivos en el ejemplo de marcado por el experto y el número de archivos relevantes que se encuentran en ese ejemplo.</span><span class="sxs-lookup"><span data-stu-id="56fce-137">In the figure above, the **Sample parameters** section of the table contains details about the number of files in the sample tagged by the expert, and the number of relevant files found in that sample.</span></span> 
  
<span data-ttu-id="56fce-p111">La sección **parámetros de población** de la tabla contiene los resultados de pruebas, incluidos la población de conjunto de revisión de los archivos con una puntuación por debajo del límite seleccionado y población "El resto" de los archivos con una puntuación por encima del límite seleccionado. Para cada población, se muestran los resultados siguientes:</span><span class="sxs-lookup"><span data-stu-id="56fce-p111">The **Population parameters** section of the table contains the test results, including the Review set population of files with a score below the selected cutoff and "The Rest" population of files with a score above the selected cutoff. For each population, the following results are displayed:</span></span> 
  
- <span data-ttu-id="56fce-140">Incluye archivos con % lectura - corte indicado</span><span class="sxs-lookup"><span data-stu-id="56fce-140">Includes files with read % - Stated cutoff</span></span>
    
- <span data-ttu-id="56fce-141">El número total de archivos</span><span class="sxs-lookup"><span data-stu-id="56fce-141">The total number of files</span></span> 
    
- <span data-ttu-id="56fce-142">El número estimado de archivos relevantes</span><span class="sxs-lookup"><span data-stu-id="56fce-142">The estimated number of relevant files</span></span> 
    
- <span data-ttu-id="56fce-143">La flexibilidad estimada</span><span class="sxs-lookup"><span data-stu-id="56fce-143">The estimated richness</span></span> 
    
- <span data-ttu-id="56fce-144">El costo promedio de revisión de buscar el otro archivo relevante</span><span class="sxs-lookup"><span data-stu-id="56fce-144">The average review cost of finding another relevant file</span></span>
    
## <a name="testing-the-slice"></a><span data-ttu-id="56fce-145">Las pruebas del sector</span><span class="sxs-lookup"><span data-stu-id="56fce-145">Testing the slice</span></span>

<span data-ttu-id="56fce-146">"Probar el sector" prueba realiza pruebas similar a "Probar el resto" probar, pero a un segmento del archivo establecer tal como se especifica en % de lectura de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="56fce-146">The "Test the Slice" test performs testing similar to the "Test the Rest" test, but to a segment of the file set as specified by Relevance Read %.</span></span>
  
1. <span data-ttu-id="56fce-147">Abrir la **la relevancia \> prueba** ficha.</span><span class="sxs-lookup"><span data-stu-id="56fce-147">Open the **Relevance \> Test** tab.</span></span> 
    
2. <span data-ttu-id="56fce-p112">En la ficha **probar** , haga clic en **probar de nuevo**. Se muestra el cuadro de diálogo **Crear prueba** .</span><span class="sxs-lookup"><span data-stu-id="56fce-p112">In the **Test** tab, click **New test**. The **Create test** dialog is displayed.</span></span> 
    
3. <span data-ttu-id="56fce-150">En **nombre de la prueba** y **Descripción**, escriba la información.</span><span class="sxs-lookup"><span data-stu-id="56fce-150">In **Test name** and **Description**, type the information.</span></span>
    
4. <span data-ttu-id="56fce-151">En la lista **tipo de prueba** , seleccione **prueba del sector**.</span><span class="sxs-lookup"><span data-stu-id="56fce-151">In the **Test type** list, select **Test the Slice**.</span></span>
    
5. <span data-ttu-id="56fce-152">En la lista de **problemas** , seleccione el nombre del problema.</span><span class="sxs-lookup"><span data-stu-id="56fce-152">In the **Issue** list, select the issue name.</span></span> 
    
6. <span data-ttu-id="56fce-153">En la lista **de carga** , seleccione la carga.</span><span class="sxs-lookup"><span data-stu-id="56fce-153">In the **Load** list, select the load.</span></span> 
    
7. <span data-ttu-id="56fce-154">En **% lectura entre**, acepte los valores de gama alta y baja de predeterminada o seleccione los valores para las puntuaciones el límite de la relevancia.</span><span class="sxs-lookup"><span data-stu-id="56fce-154">In **Read % between**, accept the default low and high range values or select values for the cutoff Relevance scores.</span></span> 
    
8. <span data-ttu-id="56fce-155">En **establecer tamaño**, seleccione un valor o acepte el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="56fce-155">In **Set size**, select a value or accept the default value.</span></span>
    
    <span data-ttu-id="56fce-156">Los iconos de restauración restaurará el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="56fce-156">The restore icons will restore the default value.</span></span>
    
9. <span data-ttu-id="56fce-p113">Haga clic en **Iniciar etiquetado**. Se genera una muestra de prueba.</span><span class="sxs-lookup"><span data-stu-id="56fce-p113">Click **Start tagging**. A test sample is generated.</span></span>
    
10. <span data-ttu-id="56fce-159">Revisar y marcar cada uno de los archivos en el **la relevancia \> etiqueta** ficha y cuando haya terminado, haga clic en **calcular**.</span><span class="sxs-lookup"><span data-stu-id="56fce-159">Review and tag each of the files in the **Relevance \> Tag** tab and when done, click **Calculate**.</span></span> 
    
11. <span data-ttu-id="56fce-160">En la ficha de prueba, puede hacer clic en **los resultados de la vista** para ver los resultados de pruebas.</span><span class="sxs-lookup"><span data-stu-id="56fce-160">In the Test tab, you can click **View results** to see the test results.</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="56fce-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="56fce-161">See also</span></span>

[<span data-ttu-id="56fce-162">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="56fce-162">Office 365 Advanced eDiscovery</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="56fce-163">Evaluación de descripción en la relevancia</span><span class="sxs-lookup"><span data-stu-id="56fce-163">Understanding Assessment in Relevance</span></span>](assessment-in-relevance-in-advanced-ediscovery.md)
  
[<span data-ttu-id="56fce-164">Etiquetas temáticas y evaluación</span><span class="sxs-lookup"><span data-stu-id="56fce-164">Tagging and Assessment</span></span>](tagging-and-assessment-in-advanced-ediscovery.md)
  
[<span data-ttu-id="56fce-165">Etiquetado y formación de relevancia</span><span class="sxs-lookup"><span data-stu-id="56fce-165">Tagging and Relevance training</span></span>](tagging-and-relevance-training-in-advanced-ediscovery.md)
  
[<span data-ttu-id="56fce-166">Análisis de la relevancia de seguimiento</span><span class="sxs-lookup"><span data-stu-id="56fce-166">Tracking Relevance analysis</span></span>](track-relevance-analysis-in-advanced-ediscovery.md)
  
[<span data-ttu-id="56fce-167">Decidir en función de los resultados</span><span class="sxs-lookup"><span data-stu-id="56fce-167">Deciding based on the results</span></span>](decision-based-on-the-results-in-advanced-ediscovery.md)

