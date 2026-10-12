# AI Engineering (Chip Huyen): guía de preguntas

## Cómo usar esta guía

1. **Antes de leer cada capítulo:** mirá los títulos de las secciones, el *Summary* del final y respondé las preguntas de **Antes de leer** con lo que ya sabés o intuís. Anotá tus respuestas: al terminar las vas a comparar.
2. **Al terminar cada sección:** cerrá el libro y respondé por escrito las preguntas de esa sección. Si no te sale una, ahí tenés una laguna: volvé a esa parte del libro.
3. **Al terminar el capítulo:** respondé los **Escenarios integradores** sin mirar el libro y releé solo las partes que fallaste.
4. **Hacé la práctica del capítulo.** Es donde los conceptos pasan de "lo entiendo" a "lo sé usar".
5. **Completá el glosario** con tus palabras, no con las del libro.
6. **Repasá:** a la semana y al mes, elegí 5–10 preguntas sueltas de capítulos anteriores y respondelas de memoria. Anotá en el *Registro de repaso* las que fallaste.

Marcá con `[x]` cada pregunta que ya podés responder bien sin mirar el libro.

Las preguntas siguen el orden de las secciones del libro (los títulos están en inglés, tal como aparecen, para que las ubiques rápido). Si una sesión de estudio te queda corta, priorizá las [E] y los escenarios: son las que más lagunas detectan.

**Leyenda de niveles**

- **[R] Recordar:** definiciones y hechos.
- **[E] Entender:** el porqué, los trade-offs y cuándo conviene o no conviene algo.
- **[A] Aplicar:** escenarios donde tenés que tomar una decisión con lo que aprendiste. La mayoría están ambientados en FinTech.

---

## Preface

- [ ] [R] ¿Cómo define la autora qué es *AI engineering* y qué tipos de modelos entran dentro de "foundation models" en este libro?
- [ ] [E] ¿Qué tres criterios usó la autora para decidir qué contenidos iban a "durar" y cuáles no? ¿Qué dice la *Lindy's Law*?
- [ ] [R] ¿Qué NO es este libro (dos cosas) y qué conceptos previos de probabilidad, ML y métricas recomienda conocer?
- [ ] [E] Según la sección *Navigating This Book*, ¿de qué tres aspectos depende la calidad de la respuesta de un modelo (además de su configuración de generación), y qué capítulo se ocupa de cada uno?
- [ ] [E] ¿En qué se diferencia el foco de este libro (AIE) del de *Designing Machine Learning Systems* (DMLS)?

---

## Capítulo 1: Introduction to Building AI Applications with Foundation Models

### Antes de leer

- [ ] ¿Qué creés que diferencia a un "foundation model" de un modelo de ML tradicional, como un clasificador de fraude?
- [ ] Si tuvieras que construir hoy un chatbot para un banco, ¿por dónde arrancarías: entrenando un modelo, usando una API o de otra forma? ¿Por qué?
- [ ] ¿Qué pensás que hace un *AI engineer* que no hace un *ML engineer*?

### 1.1 The Rise of AI Engineering

#### From Language Models to Large Language Models

- [ ] [R] ¿Qué información codifica un *language model*?
- [ ] [R] ¿Qué es un *token*, qué es la *tokenization* y qué es el *vocabulary* de un modelo? ¿Cuántas palabras son aproximadamente 100 tokens en GPT-4?
- [ ] [E] ¿Cuáles son las tres razones por las que los modelos usan tokens como unidad en lugar de palabras o caracteres?
- [ ] [R] ¿Qué diferencia hay entre un *masked language model* y un *autoregressive language model*? Nombrá un ejemplo de cada uno y para qué tareas se usa cada tipo.
- [ ] [E] ¿Por qué se dice que un language model es una "completion machine"? ¿Cómo se puede convertir una tarea de clasificación (por ejemplo, detectar spam) en una tarea de completion?
- [ ] [E] ¿Por qué *completion* no es lo mismo que mantener una conversación?
- [ ] [R] ¿Qué es *supervision* y qué es *self-supervision*? ¿En qué se diferencia self-supervision de *unsupervised learning*?
- [ ] [E] ¿Por qué la self-supervision fue la clave para que los language models pudieran escalar hasta convertirse en LLMs? Usá el ejemplo del costo de etiquetar ImageNet.
- [ ] [R] ¿Para qué sirven los tokens especiales `<BOS>` y `<EOS>`? ¿Por qué `<EOS>` es especialmente importante?
- [ ] [R] ¿Qué es un *parameter* de un modelo y cómo se suele medir el tamaño de un modelo?
- [ ] [E] ¿Por qué los modelos más grandes necesitan más datos de entrenamiento, aunque parezca contraintuitivo?

#### From Large Language Models to Foundation Models

- [ ] [R] ¿Qué es un modelo *multimodal* y qué es un LMM (*large multimodal model*)?
- [ ] [E] ¿Qué dos cosas significa la palabra "foundation" en "foundation model"?
- [ ] [R] ¿Cómo se entrenó CLIP sin etiquetado manual? ¿Qué es *natural language supervision*? ¿CLIP es generativo?
- [ ] [E] ¿Qué significa el paso de modelos *task-specific* a modelos *general-purpose*? ¿Qué ventajas siguen teniendo los modelos task-specific?
- [ ] [R] ¿Cuáles son las tres técnicas más comunes para adaptar un modelo a tus necesidades, según el ejemplo de las descripciones de productos?

#### From Foundation Models to AI Engineering

- [ ] [R] ¿Cuáles son los tres factores que, según la autora, crearon las condiciones para el crecimiento del AI engineering?
- [ ] [E] ¿Qué es el enfoque *model as a service* y por qué bajó tanto la barrera de entrada?
- [ ] [E] ¿Por qué la autora eligió el término "AI engineering" y no "ML engineering" o algún término terminado en "Ops"?

### 1.2 Foundation Model Use Cases

- [ ] [R] ¿Cuáles son las ocho categorías de casos de uso que propone la autora?
- [ ] [E] ¿Por qué las empresas despliegan antes aplicaciones internas (por ejemplo, knowledge management) que aplicaciones de cara al cliente? ¿Y por qué muchas aplicaciones siguen siendo *close-ended*, como la clasificación?
- [ ] [R] ¿Qué significa que una ocupación esté "expuesta" a la IA según Eloundou et al. (2023)? ¿Qué ocupaciones financieras aparecen con 100% de exposición?
- [ ] [E] ¿En qué tipos de tareas de software engineering la IA aumenta más la productividad y en cuáles casi nada, según McKinsey?
- [ ] [E] ¿Por qué la escritura es un caso ideal para la IA? ¿Qué mostró el estudio del MIT sobre la diferencia de calidad entre trabajadores?
- [ ] [R] ¿Qué es *talk-to-your-docs*? ¿Qué hace la plantilla "Fast Breakdown" de Instacart?
- [ ] [R] ¿Qué es IDP (*intelligent data processing*) y qué ejemplos simples y complejos de extracción de datos menciona el libro?
- [ ] [R] ¿Qué es un *agent* según la definición de este capítulo?

### 1.3 Planning AI Applications

#### Use Case Evaluation

- [ ] [R] ¿Cuáles son los tres niveles de riesgo/oportunidad que motivan a construir una aplicación de IA, ordenados de mayor a menor?
- [ ] [E] ¿Cuándo conviene hacer la IA *in-house* y cuándo comprar una solución, según el motivo por el que la construís?
- [ ] [R] Explicá las tres dimensiones del rol de la IA en un producto: *critical vs. complementary*, *reactive vs. proactive* y *dynamic vs. static*.
- [ ] [E] ¿Por qué las funciones proactivas suelen tener una exigencia de calidad más alta que las reactivas?
- [ ] [R] ¿Qué es *human-in-the-loop*? Describí las tres etapas del framework *Crawl-Walk-Run* de Microsoft.
- [ ] [E] ¿Cuáles son los tres tipos de ventaja competitiva (*moats*) en IA? ¿Por qué la ventaja de datos es "más matizada" y cómo puede aprovecharla una startup?
- [ ] [E] ¿Qué riesgo corre una aplicación construida como una "capa" sobre un foundation model cuando el modelo mejora? Usá el ejemplo del parser de PDFs.

#### Setting Expectations, Milestone Planning y Maintenance

- [ ] [R] ¿Qué grupos de métricas pueden definir el *usefulness threshold* de un producto? ¿Qué significan TTFT y TPOT?
- [ ] [E] ¿Por qué hay que evaluar los modelos existentes antes de planificar los milestones?
- [ ] [E] ¿Qué es el "last mile challenge"? ¿Qué le pasó a LinkedIn entre el 80% y el 95% de la experiencia que buscaban?
- [ ] [E] ¿Qué cambios del ecosistema de IA dificultan el mantenimiento de un producto? Distinguí entre cambios buenos que igual generan fricción, cambios fáciles de adaptar y cambios difíciles o hasta fatales (regulación, propiedad intelectual).

### 1.4 The AI Engineering Stack

- [ ] [R] ¿Cuáles son las tres capas del stack de IA y qué incluye cada una?
- [ ] [E] ¿Qué principios del ML engineering tradicional siguen valiendo en AI engineering?
- [ ] [R] ¿Cuáles son las tres grandes diferencias entre AI engineering y ML engineering?
- [ ] [E] ¿En qué se diferencian las técnicas de adaptación *prompt-based* del *finetuning*? ¿Qué se gana y qué se pierde con cada una?
- [ ] [R] Diferenciá *training*, *pre-training*, *finetuning* y *post-training*. ¿Por qué la quantization cambia los pesos pero no se considera training?
- [ ] [E] ¿Por qué decir que "entrenaste" a ChatGPT dándole tus textos en el prompt es técnicamente incorrecto?
- [ ] [E] ¿Cómo cambian el modeling/training, el dataset engineering y la inference optimization cuando se trabaja con foundation models en lugar de ML tradicional?
- [ ] [E] ¿Por qué la generación autoregressive hace que la latencia sea un desafío tan grande?
- [ ] [R] ¿Cuáles son las tres responsabilidades de la capa de application development y cómo cambia su importancia respecto del ML tradicional?
- [ ] [E] ¿Qué muestra la historia de Gemini, MMLU y CoT@32 sobre lo difícil que es comparar modelos?
- [ ] [E] ¿Por qué el AI engineering se acerca al desarrollo full-stack? ¿Cómo cambia el orden "datos → modelo → producto"?

### Escenarios integradores

- [ ] [A] Una billetera virtual quiere un asistente que responda consultas de clientes sobre movimientos y comisiones. Usando *Crawl-Walk-Run*, describí cómo irías aumentando la automatización y qué métrica usarías para decidir pasar de una etapa a la siguiente.
- [ ] [A] Un banco argentino evalúa construir un sistema de IA que lea legajos de crédito (recibos de sueldo, extractos, DNI) y arme un resumen para el analista. ¿Este uso de la IA es *critical* o *complementary*? ¿Reactivo o proactivo? ¿Qué *usefulness threshold* definirías antes de ponerlo en producción?
- [ ] [A] Querés fundar una startup que ofrece un "analista financiero con IA" para PyMEs construido sobre la API de un modelo comercial. ¿Cuál sería tu *moat*? ¿Qué pasa si el proveedor del modelo lanza esa misma función?
- [ ] [A] Tu equipo armó en dos semanas una demo que responde bien el 80% de las preguntas sobre productos de inversión. El gerente quiere lanzarla el mes próximo. ¿Qué le dirías, basándote en el last mile challenge y en los riesgos de mantenimiento y regulación?

### Práctica del capítulo

Elegí una tarea financiera concreta (por ejemplo, clasificar transacciones bancarias en categorías como "supermercado", "servicios" o "transferencia"). Escribí un programa chico (Spring AI o Python) que la resuelva con la API de un modelo usando solo un prompt. Probalo con 15–20 transacciones reales o inventadas y anotá:

- Cuántas acierta (es tu línea de base).
- Cuántos tokens consume cada request y cuánto cuesta.
- Cuánto tarda en responder.

**Qué aprendés:** que con un modelo off-the-shelf llegás rápido a un resultado "decente", y que medir calidad, costo y latencia desde el día uno es lo que define el usefulness threshold.

### Glosario para completar

- **Language model**: 
- **Token / tokenization / vocabulary**: 
- **Masked vs. autoregressive language model**: 
- **Self-supervision**: 
- **Parameter**: 
- **Foundation model**: 
- **LMM (large multimodal model)**: 
- **Model as a service**: 
- **Prompt engineering**: 
- **RAG**: 
- **Finetuning / post-training / pre-training**: 
- **Human-in-the-loop**: 
- **Usefulness threshold**: 
- **TTFT / TPOT**: 
- **Inference**: 

---

## Capítulo 2: Understanding Foundation Models

### Antes de leer

- [ ] Si un modelo responde distinto cada vez que le hacés la misma pregunta, ¿a qué creés que se debe?
- [ ] ¿Por qué pensás que un modelo "inventa" datos (alucina) en lugar de decir "no sé"?
- [ ] ¿Qué creés que determina si un modelo es mejor que otro: su tamaño, sus datos, otra cosa?

### 2.1 Training Data

- [ ] [R] ¿Qué es Common Crawl y qué es C4? ¿Qué problemas de calidad tienen?
- [ ] [E] ¿Qué consecuencias tiene el enfoque "use what we have, not what we want" para las tareas que a vos te importan?
- [ ] [E] ¿Por qué entrenar con "todos los datos posibles" no siempre da mejores resultados? Usá el ejemplo del modelo de código de 1,3B parámetros de Gunasekar et al.

#### Multilingual Models

- [ ] [R] ¿Qué es un idioma *low-resource*? ¿Qué porcentaje de Common Crawl es inglés?
- [ ] [E] ¿Cuáles son las causas por las que los modelos rinden peor en idiomas distintos del inglés? ¿La subrepresentación es la única?
- [ ] [E] ¿Por qué traducir todas las consultas al inglés, responder y volver a traducir no es una solución ideal? Nombrá los dos problemas.
- [ ] [E] ¿Por qué el mismo contenido puede ser más lento y más caro en un idioma que en otro? ¿Qué tiene que ver la tokenization?

#### Domain-Specific Models

- [ ] [E] ¿Por qué un modelo general difícilmente rinda bien en tareas como drug discovery o screening de cáncer? ¿Qué tienen en común esos datos?
- [ ] [R] Nombrá dos o tres ejemplos de modelos domain-specific que menciona el libro y en qué datos se entrenaron.

### 2.2 Modeling

#### Model Architecture

- [ ] [R] ¿Qué es la arquitectura seq2seq? ¿Qué hacen el encoder y el decoder, y qué tipo de red usaban?
- [ ] [E] ¿Cuáles son los dos problemas de seq2seq que resolvió el transformer? Explicá la analogía de "responder sobre un libro usando solo el resumen".
- [ ] [E] Si el transformer procesa el input en paralelo, ¿por qué la generación sigue siendo secuencial? Explicá las etapas de *prefill* y *decode*.
- [ ] [R] En el attention mechanism, ¿qué representan los vectores *query* (Q), *key* (K) y *value* (V)? Usá la analogía del libro (páginas, números de página, contenido).
- [ ] [E] ¿Cómo se calcula cuánta atención darle a cada token previo? ¿Por qué secuencias más largas hacen tan difícil extender el context length en un transformer?
- [ ] [R] ¿Qué es *multi-headed attention*? En Llama 2-7B, ¿por qué cada vector K, V y Q se divide en 32 vectores de dimensión 128?
- [ ] [R] ¿Qué dos módulos contiene un *transformer block*? ¿Qué hace una función de activación como ReLU y por qué es necesaria?
- [ ] [R] ¿Qué hacen el módulo de embedding (antes de los bloques) y la capa de salida o *unembedding layer* (después)? ¿Qué relación hay entre los *position indices* y el context length máximo?
- [ ] [R] ¿Qué cuatro valores determinan el tamaño de un transformer? ¿Aumentar el context length aumenta la cantidad de parámetros?
- [ ] [E] ¿Por qué es tan difícil que una arquitectura nueva reemplace al transformer?
- [ ] [R] ¿Qué son RWKV y los SSMs (*state space models*)? ¿Qué ventaja muestra Mamba sobre el transformer en cómo escala con el largo de la secuencia? ¿Qué es Jamba?

#### Model Size

- [ ] [R] ¿Cuánta memoria de GPU necesitás, como mínimo, para hacer inferencia con un modelo de 7B parámetros guardados en 2 bytes cada uno?
- [ ] [R] ¿Qué es un modelo *sparse*? ¿Qué es un *mixture-of-experts* (MoE)?
- [ ] [E] Mixtral 8x7B tiene 46,7B parámetros, pero cuesta y tarda como un modelo de 12,9B. ¿Por qué?
- [ ] [E] ¿Por qué el número de tokens es mejor medida del tamaño de un dataset que el número de muestras? ¿Qué diferencia hay entre los tokens del dataset y los *training tokens*? ¿Qué es un *epoch*?
- [ ] [R] Diferenciá FLOPs de FLOP/s. ¿Qué es la *utilization* y qué valores se consideran buenos?
- [ ] [R] ¿Cuáles son los tres números que indican la escala de un modelo y de qué es proxy cada uno?
- [ ] [R] ¿Qué dice la *Chinchilla scaling law*? ¿Cuántos training tokens necesita un modelo de 3B parámetros para ser *compute-optimal*?
- [ ] [E] ¿Por qué Meta eligió modelos Llama más chicos de lo que la scaling law recomendaba para su presupuesto? ¿Qué te dice eso sobre "calidad vs. usabilidad"?
- [ ] [E] ¿Por qué pasar de 90% a 95% de accuracy es mucho más caro que pasar de 85% a 90%?
- [ ] [R] ¿Qué diferencia hay entre un *parameter* y un *hyperparameter*? Dá ejemplos de los dos tipos de hyperparameters.
- [ ] [E] ¿Qué es *scaling extrapolation* y por qué es necesaria? ¿Qué son las *emergent abilities* y por qué complican la extrapolación?
- [ ] [E] ¿Cuáles son los dos cuellos de botella visibles para seguir escalando modelos? ¿Por qué los datos propietarios se vuelven una ventaja competitiva?
- [ ] [E] ¿Qué riesgo implica que internet se esté llenando de contenido generado por IA para el entrenamiento de modelos futuros?

### 2.3 Post-Training

- [ ] [R] ¿Cuáles son los dos problemas que tiene un modelo recién pre-entrenado y que el post-training busca resolver?
- [ ] [R] ¿Cuáles son los dos pasos típicos del post-training?
- [ ] [E] ¿Qué optimiza el pre-training (calidad a nivel token) y qué optimiza el post-training (calidad de la respuesta completa)? Explicá la metáfora del Shoggoth con cara sonriente.

#### Supervised Finetuning

- [ ] [R] ¿Qué es *demonstration data* y por qué al SFT también se lo llama *behavior cloning*?
- [ ] [E] ¿Por qué generar demonstration data es tanto más caro que etiquetar imágenes? ¿Qué perfil tenían los labelers de InstructGPT?
- [ ] [E] ¿Qué alternativas a la anotación humana cara mencionan (LAION, heurísticas de DeepMind para Gopher, datos sintéticos)? ¿Qué problema de sesgo tuvo LAION?

#### Preference Finetuning

- [ ] [E] ¿Por qué la demonstration data no alcanza? ¿Qué le enseña el preference finetuning al modelo que el SFT no?
- [ ] [R] ¿Cuáles son las dos partes de RLHF? ¿Qué es DPO y por qué Meta lo eligió para Llama 3?
- [ ] [E] ¿Por qué se usa *comparison data* (prompt, respuesta ganadora, respuesta perdedora) en vez de pedirles a los labelers un puntaje directo (*pointwise evaluation*)?
- [ ] [E] ¿Cómo se entrena un reward model que devuelve un puntaje concreto si solo tenés comparaciones? Explicá la intuición de la función de pérdida, sin la fórmula.
- [ ] [R] ¿Qué es la estrategia *best of N* y qué empresas la usan con su reward model en lugar de hacer RL?

### 2.4 Sampling

#### Sampling Fundamentals

- [ ] [R] ¿Qué es un *logit*? ¿Por qué los logits no son probabilidades y cómo se convierten en probabilidades?
- [ ] [E] ¿Qué es *greedy sampling*? ¿Por qué funciona bien para clasificación pero genera textos aburridos en un language model?

#### Sampling Strategies

- [ ] [E] ¿Qué hace la *temperature* con los logits? ¿Qué pasa con temperatura alta y con temperatura baja? ¿Qué significa en la práctica "temperatura 0"?
- [ ] [R] ¿Qué son los *logprobs*, por qué se usa escala logarítmica (el problema de underflow) y para qué sirven? ¿Por qué muchos proveedores no los exponen?
- [ ] [E] ¿Qué es *top-k* y qué problema de cómputo resuelve?
- [ ] [E] ¿Qué es *top-p* (*nucleus sampling*) y por qué es más dinámico que top-k? Usá el ejemplo de "¿Te gusta la música? Respondé sí o no".
- [ ] [E] ¿Qué son las *stopping conditions*? ¿Qué riesgo tienen si querés que el modelo devuelva JSON?

#### Test Time Compute

- [ ] [R] ¿Qué es *test time compute*? ¿Qué es *beam search*?
- [ ] [E] ¿Por qué no podés elegir la mejor salida usando directamente la suma de logprobs? ¿Por qué se usa el promedio?
- [ ] [E] ¿Qué formas de elegir la mejor salida menciona el libro? (probabilidad, reward model/verifier, heurísticas, la respuesta más frecuente.)
- [ ] [E] ¿Qué mostró OpenAI sobre usar un *verifier* frente a aumentar el tamaño del modelo? ¿Qué pasó al pasar de 400 salidas?
- [ ] [E] ¿Qué significa que un modelo sea *robust*? ¿Por qué a un modelo poco robusto le sirve más generar varias salidas?

#### Structured Outputs

- [ ] [R] ¿En qué dos escenarios son necesarios los *structured outputs*? ¿Qué es *semantic parsing*?
- [ ] [R] ¿En qué cinco capas del stack se puede guiar al modelo hacia salidas estructuradas? ¿Cuáles son "curitas" y cuáles son el "tratamiento intensivo"?
- [ ] [E] ¿Qué garantiza y qué NO garantiza el *JSON mode* de una API?
- [ ] [E] ¿Por qué el post-processing funciona sorprendentemente bien? ¿Qué logró el parser YAML defensivo de LinkedIn y por qué eligieron YAML en vez de JSON?
- [ ] [E] ¿Cómo funciona el *constrained sampling* sobre el vector de logits? ¿Cuáles son sus desventajas?
- [ ] [E] ¿Por qué el finetuning es la forma más efectiva y general de obtener un formato? ¿Qué es agregar un *classifier head*?

#### The Probabilistic Nature of AI

- [ ] [R] ¿Cuáles son los dos escenarios de *inconsistency*?
- [ ] [E] ¿Qué podés hacer para mitigar el escenario "mismo input, distinto output" (cache, sampling variables, *seed*)? ¿Por qué, aun así, no hay garantía del 100%?
- [ ] [R] ¿Cuáles son las dos hipótesis sobre por qué alucinan los modelos? Explicá *self-delusion* / *snowballing hallucinations* y la del desajuste de conocimiento interno entre modelo y labeler.
- [ ] [E] ¿Qué soluciones propone cada hipótesis? ¿RLHF reduce o empeora las alucinaciones según InstructGPT?
- [ ] [E] ¿Por qué pedir respuestas concisas o agregar "si no estás seguro, decí que no sabés" puede ayudar a reducir alucinaciones?

### Escenarios integradores

- [ ] [A] Estás construyendo un clasificador de transacciones para un banco que necesita la categoría en formato JSON, siempre válido. Ordená qué técnicas probarías primero y cuáles después (prompting, post-processing, test time compute, constrained sampling, finetuning) y justificá el orden por costo y efectividad.
- [ ] [A] Un asistente de una fintech a veces dice que una transferencia tiene comisión y otras veces que no, ante la misma pregunta. ¿Qué causas posibles ves y qué ajustes de sampling y de sistema harías?
- [ ] [A] Tu chatbot de inversiones le inventó a un cliente el rendimiento histórico de un fondo. Usando las dos hipótesis de alucinación, explicá por qué pudo pasar y qué harías para mitigarlo.
- [ ] [A] Tu empresa atiende clientes en Brasil y Argentina y paga la API por token. ¿Qué tendrías que medir antes de elegir modelo, considerando el idioma y la tokenization?
- [ ] [A] Para extraer datos de fotos de facturas, el modelo acierta solo la mitad de las veces y en las demás dice que la imagen "está borrosa". ¿Qué estrategia de test time compute aplicarías y cuánto aumenta el costo?

### Práctica del capítulo

Usá una API que devuelva *logprobs* (por ejemplo, la de OpenAI) con un prompt de clasificación de riesgo: "¿Esta transacción es sospechosa? Respondé SÍ o NO", más una descripción de la transacción. Para 10 transacciones:

1. Corré cada prompt 5 veces con temperatura 0, 5 veces con 0,7 y 5 veces con 1,5. Anotá cuántas veces cambia la respuesta.
2. Mirá los logprobs de "SÍ" y "NO" y convertilos en probabilidades.
3. Implementá *best of N* (o "la respuesta más frecuente") con N = 5 y compará contra una sola llamada.

**Qué aprendés:** a ver en la práctica cómo temperature y sampling generan inconsistencia, y cómo los logprobs te dan una medida de "confianza" útil para clasificación.

### Glosario para completar

- **Common Crawl / C4**: 
- **Low-resource language**: 
- **Transformer / attention mechanism**: 
- **Query, key, value**: 
- **Prefill / decode**: 
- **Mixture-of-experts (MoE)**: 
- **FLOPs vs. FLOP/s**: 
- **Chinchilla scaling law**: 
- **Hyperparameter**: 
- **Supervised finetuning (SFT) / demonstration data**: 
- **RLHF / reward model / DPO**: 
- **Logits / softmax / logprobs**: 
- **Temperature / top-k / top-p**: 
- **Test time compute / best of N**: 
- **Constrained sampling**: 
- **Hallucination / inconsistency**: 

---

## Capítulo 3: Evaluation Methodology

### Antes de leer

- [ ] ¿Cómo evaluarías hoy si las respuestas de un chatbot son "buenas"? ¿Qué harías concretamente?
- [ ] ¿Te parece confiable usar una IA para evaluar las respuestas de otra IA? ¿Por qué sí o por qué no?
- [ ] ¿Qué diferencia hay entre evaluar un clasificador de fraude y evaluar un asistente que escribe respuestas libres?

### 3.1 Challenges of Evaluating Foundation Models

- [ ] [E] ¿Por qué cuanto más inteligente es un modelo, más difícil es evaluarlo? Usá el ejemplo del resumen de un libro.
- [ ] [E] ¿Por qué la naturaleza *open-ended* de los foundation models rompe el enfoque tradicional de comparar contra *ground truths*?
- [ ] [E] ¿Qué problema agrega que los modelos se traten como *black boxes*?
- [ ] [R] ¿Qué significa que un benchmark esté *saturated*? Dá ejemplos de benchmarks que se saturaron y fueron reemplazados.
- [ ] [E] ¿Cómo se amplió el alcance de la evaluación con modelos *general-purpose*?
- [ ] [E] Según la autora, ¿qué hace la mayoría de los equipos para evaluar (eyeballing, *vibe check*) y por qué no alcanza para iterar una aplicación?

### 3.2 Understanding Language Modeling Metrics

- [ ] [R] ¿Cuáles son las cuatro métricas de language modeling relacionadas entre sí? ¿Por qué se puede calcular cualquiera conociendo otra?
- [ ] [E] ¿Por qué el rendimiento del componente de language model sirve como indicador del rendimiento en tareas downstream?

#### Entropy y Cross Entropy

- [ ] [E] ¿Qué mide la *entropy*? Explicá el ejemplo del cuadrado con un lenguaje de 2 tokens y otro de 4. ¿Qué relación hay entre entropy y lo predecible que es un lenguaje?
- [ ] [R] ¿De qué dos cosas depende la *cross entropy* de un modelo sobre un dataset? ¿Qué rol cumple la *KL divergence*?
- [ ] [E] Si un modelo aprendiera perfectamente sus datos de entrenamiento, ¿cuánto valdrían su cross entropy y la KL divergence?

#### Bits-per-Character, Bits-per-Byte y Perplexity

- [ ] [E] ¿Por qué *bits per token* no sirve para comparar modelos distintos? ¿Por qué BPB es más estándar que BPC?
- [ ] [E] ¿Qué relación hay entre cross entropy y la capacidad de un modelo de comprimir texto?
- [ ] [R] ¿Qué es la *perplexity* y cómo se relaciona con la cross entropy? ¿Qué diferencia hay entre usar bits y *nats*?
- [ ] [E] Un modelo que codifica perfectamente los 4 tokens de posición del cuadrado, ¿qué perplexity tiene y por qué?

#### Perplexity Interpretation and Use Cases

- [ ] [E] Explicá las tres reglas generales para interpretar la perplexity (datos estructurados, tamaño del vocabulario, largo del contexto).
- [ ] [E] ¿Por qué la perplexity puede no ser un buen indicador para modelos con post-training (SFT, RLHF)? ¿Qué significa que "el post-training colapsa la entropy"?
- [ ] [E] ¿Cómo se puede usar la perplexity para detectar *data contamination*, para deduplicar datos y para detectar textos anormales?
- [ ] [R] ¿Qué necesitás de un modelo para poder calcular la perplexity de un texto?

### 3.3 Exact Evaluation

- [ ] [R] ¿Qué diferencia hay entre evaluación *exact* y evaluación *subjective*? ¿En cuál cae AI as a judge?

#### Functional Correctness

- [ ] [R] ¿Qué es *functional correctness* y por qué es la métrica "definitiva"? ¿Por qué no siempre se puede automatizar?
- [ ] [R] ¿Qué es *execution accuracy*? Nombrá benchmarks de código y de text-to-SQL que la usan.
- [ ] [E] ¿Cómo se calcula *pass@k*? Si hay 10 problemas y el modelo resuelve 5 con k = 3, ¿cuánto da pass@3? ¿Por qué pass@1 debería ser menor que pass@10?
- [ ] [R] ¿Qué otros tipos de tareas, además del código, se pueden evaluar con functional correctness?

#### Similarity Measurements Against Reference Data

- [ ] [R] ¿Qué son *reference responses* (*ground truths*, *canonical responses*)? ¿Qué diferencia hay entre métricas *reference-based* y *reference-free*?
- [ ] [R] ¿Cuáles son las cuatro formas de medir la similitud entre dos textos abiertos?
- [ ] [E] ¿Para qué tareas sirve el *exact match* y para cuáles no? ¿Qué problema tiene la variante "aceptar si la salida contiene la referencia"? (Ejemplo de Ana Frank.)
- [ ] [R] ¿Qué es la *lexical similarity*? Explicá *fuzzy matching* / *edit distance* y la *n-gram similarity*.
- [ ] [R] Nombrá métricas comunes de lexical similarity (BLEU, ROUGE, etc.).
- [ ] [E] ¿Cuáles son las desventajas de la lexical similarity? Explicá el caso de Fuyu y el hallazgo de OpenAI sobre BLEU en HumanEval.
- [ ] [E] ¿Por qué "What's up?" y "How are you?" tienen baja lexical similarity pero alta *semantic similarity*? ¿Y "Let's eat, grandma" vs. "Let's eat grandma"?
- [ ] [R] ¿Cómo se calcula la *cosine similarity* entre dos embeddings y qué rango de valores tiene? Nombrá métricas de semantic similarity (BERTScore, MoverScore).
- [ ] [E] ¿De qué depende la confiabilidad de la semantic similarity y cuáles son sus desventajas?
- [ ] [R] ¿Para qué otros usos, además de evaluar, sirven las medidas de similitud? (Búsqueda, ranking, clustering, etc.)

#### Introduction to Embedding

- [ ] [R] ¿Qué es un *embedding*? ¿Qué tamaño suelen tener? Nombrá modelos que generan embeddings.
- [ ] [E] ¿Cómo sabés si un algoritmo de embeddings es bueno? ¿Qué es MTEB?
- [ ] [E] ¿Por qué los embeddings extraídos de capas intermedias de un LLM pueden ser peores que los de un modelo especializado en embeddings?
- [ ] [E] ¿Qué es un *joint embedding space* o *multimodal embedding space*? ¿Cómo se entrena CLIP y qué permite hacer (por ejemplo, buscar imágenes con texto)?

### 3.4 AI as a Judge

#### Why AI as a Judge?

- [ ] [E] ¿Cuáles son las ventajas de AI as a judge frente a evaluadores humanos y frente a métricas exactas? ¿Por qué sirve en producción sin datos de referencia?
- [ ] [R] ¿Qué nivel de acuerdo con humanos mostró GPT-4 en MT-Bench, comparado con el acuerdo entre humanos?

#### How to Use AI as a Judge

- [ ] [R] ¿Cuáles son las tres formas de usar un AI judge? (Evaluar una respuesta sola, compararla con una referencia, comparar dos respuestas.)
- [ ] [R] ¿Qué tres cosas tiene que explicar claramente el prompt de un juez?
- [ ] [E] ¿Qué tipo de sistema de puntuación funciona mejor con AI judges (clasificación, discreto o continuo) y por qué? ¿Qué rango discreto se recomienda?
- [ ] [E] ¿Por qué se dice que un AI judge "no es solo un modelo, sino un sistema"? ¿Qué cambia si modificás el prompt o los sampling parameters?

#### Limitations of AI as a Judge

- [ ] [E] ¿Por qué la inconsistencia de un juez es un problema? ¿Alcanza con agregar ejemplos al prompt? ¿Qué relación hay entre consistencia y accuracy, y qué costo extra tiene?
- [ ] [E] ¿Qué es la *criteria ambiguity*? Explicá el ejemplo de *faithfulness* en MLflow, Ragas y LlamaIndex.
- [ ] [E] Si el puntaje de coherencia de tu aplicación pasó de 90% a 92%, ¿por qué no podés concluir que mejoró sin saber nada más del juez?
- [ ] [E] ¿Cuánto aumentan el costo y la latencia los AI judges? ¿Qué es *spot-checking* y qué trade-off implica?
- [ ] [R] Explicá tres sesgos de los AI judges: *self-bias*, *first-position bias* y *verbosity bias*. ¿En qué se diferencia el sesgo de posición de la IA del de los humanos?
- [ ] [E] ¿Qué problemas de privacidad y propiedad intelectual trae usar un modelo propietario como juez?

#### What Models Can Act as Judges?

- [ ] [E] ¿Qué ventajas y desafíos tiene usar un juez más fuerte que el modelo evaluado? ¿Por qué tendría sentido generar con un modelo débil y evaluar con uno fuerte (o al revés)?
- [ ] [E] ¿Para qué sirve la *self-evaluation* o *self-critique*, a pesar del self-bias?
- [ ] [E] ¿Puede un modelo más débil juzgar a uno más fuerte? ¿Qué argumento hay a favor?
- [ ] [R] Describí los tres tipos de jueces especializados: *reward model*, *reference-based judge* y *preference model*. Dá un ejemplo de cada uno.

### 3.5 Ranking Models with Comparative Evaluation

- [ ] [R] ¿Qué diferencia hay entre *pointwise evaluation* y *comparative evaluation*? ¿Por qué comparar suele ser más fácil para calidad subjetiva?
- [ ] [E] ¿Por qué no todas las preguntas deberían resolverse por preferencia? ¿En qué tipo de aplicaciones funciona la votación por preferencia y en cuáles no?
- [ ] [R] ¿En qué se diferencia la comparative evaluation de un A/B test? ¿Qué es un *match* y qué es el *win rate*?
- [ ] [R] ¿Qué algoritmos de rating se usan (Elo, Bradley–Terry, TrueSkill)? ¿Por qué Chatbot Arena pasó de Elo a Bradley–Terry?
- [ ] [E] ¿Por qué el ranking de modelos es un problema predictivo? ¿Cómo se juzga si un ranking es correcto si no hay ground truth?

#### Challenges of Comparative Evaluation

- [ ] [E] ¿Por qué la comparative evaluation tiene un cuello de botella de escalabilidad? ¿Qué supone la *transitivity* y por qué puede no cumplirse con modelos de IA?
- [ ] [E] ¿Por qué es difícil evaluar un modelo nuevo o un modelo privado con comparative evaluation? ¿Cómo ayudan los mejores algoritmos de *matching*?
- [ ] [E] ¿Qué problemas de estandarización y control de calidad tiene el crowdsourcing de comparaciones (prompts simples como "hello", votos maliciosos, falta de contexto como RAG)? ¿Qué soluciones existen?
- [ ] [E] ¿Por qué la comparative evaluation no te dice si un modelo es "suficientemente bueno"? Si el modelo B le gana al A el 51% de las veces, ¿qué no sabés?

#### The Future of Comparative Evaluation

- [ ] [E] ¿Qué ventajas tiene la comparative evaluation a futuro? (Modelos que superan a los humanos, no se satura, es difícil de manipular.)

### Escenarios integradores

- [ ] [A] Tu equipo construyó un generador de SQL para que analistas de riesgo consulten la base de préstamos en lenguaje natural. ¿Qué método de evaluación usarías primero y por qué? ¿Qué limitaciones tendría?
- [ ] [A] Querés evaluar si las respuestas de tu chatbot de atención al cliente de una billetera virtual son fieles a la documentación oficial de comisiones. Diseñá el prompt de un AI judge: tarea, criterio y sistema de puntuación. ¿Qué sesgos tendrías que vigilar?
- [ ] [A] Tenés que elegir entre dos modelos para resumir reportes de inversión. Un compañero propone hacer una comparative evaluation con los propios analistas. ¿Funciona en este caso? ¿Qué información adicional necesitarías para decidir, considerando que el modelo B cuesta el doble?
- [ ] [A] Un proveedor te dice que su modelo tiene 95% en un benchmark de finanzas público. ¿Qué técnica de este capítulo podrías usar para sospechar *data contamination*? ¿Qué necesitarías del modelo?
- [ ] [A] Otro equipo de tu banco administra el AI judge de "toxicidad" que usa tu aplicación. Este mes el puntaje mejoró 5 puntos sin que cambiaras nada. ¿Qué le preguntarías a ese equipo y qué proceso propondrías para que no vuelva a pasar?

### Práctica del capítulo

Armá un mini set de evaluación para un asistente que responde preguntas sobre un producto financiero (por ejemplo, una tarjeta de crédito ficticia con su documento de condiciones):

1. Escribí 20 preguntas con su respuesta de referencia.
2. Generá respuestas con un modelo.
3. Evaluá cada respuesta de tres formas: *exact match*, *semantic similarity* (con un modelo de embeddings y cosine similarity) y un AI judge con un prompt que tenga criterio, escala 1–5 y ejemplos.
4. Corré el juez 3 veces sobre las mismas respuestas y medí cuánto cambia el puntaje. Probá invertir el orden en una comparación de a pares para ver si aparece el *position bias*.

**Qué aprendés:** a ver en concreto las fortalezas y debilidades de cada método, y por qué ninguno alcanza solo.

### Glosario para completar

- **Ground truth / reference response**: 
- **Benchmark saturation**: 
- **Entropy / cross entropy**: 
- **KL divergence**: 
- **Perplexity**: 
- **Data contamination**: 
- **Functional correctness / pass@k**: 
- **Exact match**: 
- **Lexical similarity (edit distance, n-grams, BLEU, ROUGE)**: 
- **Semantic similarity / cosine similarity**: 
- **Embedding / joint embedding space**: 
- **AI as a judge**: 
- **Self-bias / position bias / verbosity bias**: 
- **Reward model / preference model**: 
- **Pointwise vs. comparative evaluation**: 
- **Win rate / Elo / Bradley–Terry**: 

---

## Capítulo 4: Evaluate AI Systems

### Antes de leer

- [ ] Si tuvieras que elegir entre diez modelos para un chatbot bancario, ¿qué mirarías primero?
- [ ] ¿Qué preferirías para un banco: usar la API de un proveedor o alojar un modelo open source propio? ¿Por qué?
- [ ] ¿Cuántos ejemplos creés que necesitás para saber si un prompt nuevo es mejor que el anterior?

### 4.1 Evaluation Criteria

- [ ] [E] ¿Qué es peor, según la autora: una aplicación nunca desplegada o una desplegada que nadie sabe si funciona? ¿Por qué?
- [ ] [R] ¿Qué es *evaluation-driven development* y en qué se inspira?
- [ ] [E] ¿Por qué las aplicaciones más comunes en producción son las que tienen criterios de evaluación claros (recomendadores, fraude, código)? ¿Qué riesgo tiene enfocarse solo en ellas? (Metáfora de la llave bajo el farol.)
- [ ] [R] ¿Cuáles son los cuatro grupos de criterios de evaluación? Explicalos con el ejemplo de resumir un contrato legal.

#### Domain-Specific Capability

- [ ] [E] ¿Qué limita las capacidades de dominio de un modelo? ¿Cómo se suelen evaluar?
- [ ] [E] Además de functional correctness, ¿qué otros aspectos del código generado pueden importar (eficiencia, legibilidad) y cómo se evalúa cada uno? ¿Qué agrega BIRD-SQL?
- [ ] [E] ¿Por qué la mayoría de los benchmarks públicos usan preguntas de opción múltiple (MCQ)? ¿Qué es el *random baseline*?
- [ ] [E] ¿Cuáles son las desventajas de las MCQ? ¿Para qué capacidades sirven y para cuáles no?
- [ ] [R] ¿Por qué la clasificación es un caso especial de opción múltiple? ¿Qué métricas se usan además de accuracy?

#### Generation Capability

- [ ] [R] ¿Qué es NLG? ¿Qué miden *fluency*, *coherence*, *faithfulness* y *relevance*?
- [ ] [E] ¿Por qué fluency y coherence perdieron importancia con los modelos actuales? ¿Cuándo siguen siendo útiles?
- [ ] [R] Diferenciá *local factual consistency* de *global factual consistency*. ¿Para qué tareas importa cada una?
- [ ] [E] ¿Por qué lo más difícil de verificar la factual consistency suele ser determinar qué es un hecho? ¿Qué es la *absence of evidence fallacy*?
- [ ] [E] ¿En qué dos tipos de consultas tendía a alucinar el modelo en el proyecto de la autora? ¿Qué te dice eso sobre cómo armar un benchmark de alucinaciones?
- [ ] [R] Explicá *self-verification* (SelfCheckGPT) y *knowledge-augmented verification* (SAFE). ¿Cuáles son los cuatro pasos de SAFE?
- [ ] [R] ¿Qué es *textual entailment*? Explicá *entailment*, *contradiction* y *neutral* con el ejemplo de "Mary likes all fruits".
- [ ] [E] ¿Qué ventaja tiene entrenar un clasificador especializado en entailment (como DeBERTa) frente a usar un AI judge general?
- [ ] [R] ¿Qué es TruthfulQA? ¿Por qué la factual consistency es crítica para RAG?
- [ ] [R] ¿Cuáles son las seis categorías de contenido inseguro que menciona el libro?
- [ ] [E] ¿Qué opciones tenés para detectar contenido tóxico (AI judges generales, herramientas de moderación, clasificadores especializados)? ¿Qué ventajas tienen los clasificadores especializados?

#### Instruction-Following Capability

- [ ] [E] En el ejemplo del análisis de sentimiento que devuelve HAPPY en vez de POSITIVE, ¿qué capacidad tiene el modelo y cuál le falta?
- [ ] [E] ¿Por qué es difícil separar la capacidad de seguir instrucciones de la capacidad de dominio? (Ejemplo del poema *lục bát*.) ¿Y por qué es difícil saber si falló el modelo o la instrucción?
- [ ] [R] ¿En qué se diferencian IFEval e INFOBench? ¿Cómo verifica INFOBench instrucciones que no se pueden chequear automáticamente?
- [ ] [E] ¿Por qué deberías armar tu propio benchmark de instruction-following en lugar de confiar en IFEval o INFOBench?
- [ ] [E] ¿Para qué dos propósitos se usa el *roleplaying*? ¿Qué dos aspectos hay que evaluar de un personaje (estilo y conocimiento) y qué es el chequeo de "conocimiento negativo"?

#### Cost and Latency

- [ ] [R] ¿Qué es *Pareto optimization*? ¿Cómo se aplica cuando la latencia es un requisito no negociable?
- [ ] [E] ¿Por qué hay que distinguir entre requisitos de latencia *must-have* y *nice-to-have*?
- [ ] [E] ¿Cómo cambia el costo por token a medida que escalás, si usás una API o si alojás tu propio modelo? ¿Por qué tantos modelos tienen 7B o 65B parámetros?
- [ ] [R] ¿Qué criterios aparecen en la tabla de ejemplo para seleccionar modelos? ¿Qué diferencia hay entre *hard requirement* e *ideal*?

### 4.2 Model Selection

- [ ] [R] ¿Cuáles son los dos pasos generales del proceso de selección para cada técnica de adaptación?
- [ ] [R] Diferenciá *hard attributes* de *soft attributes*. ¿Por qué la latencia puede ser uno u otro según el caso?
- [ ] [R] ¿Cuáles son los cuatro pasos del *model selection workflow*? ¿Por qué es iterativo?

#### Model Build Versus Buy

- [ ] [R] ¿Qué diferencia hay entre un modelo *open weight* y un *open model*? ¿Cómo usa la autora el término "open source" en el libro?
- [ ] [R] ¿Qué preguntas deberías hacerte sobre la licencia de un modelo? (Uso comercial, restricciones, usar sus outputs para entrenar otros modelos.)
- [ ] [R] ¿Qué es un *inference service* y qué es una *model API*? ¿Quiénes pueden ofrecer APIs de modelos?
- [ ] [R] ¿Cuáles son los siete ejes para decidir entre usar una API o alojar tu modelo?
- [ ] [E] ¿Qué riesgos de privacidad tiene usar una API externa? Mencioná el caso de Samsung y por qué importa que los modelos memoricen datos de entrenamiento.
- [ ] [E] ¿Cómo influye la preocupación por *data lineage* y copyright en la elección entre modelos open source y comerciales? ¿Por qué un contrato con un proveedor comercial puede protegerte?
- [ ] [E] ¿Por qué la autora cree que el mejor modelo open source va a seguir detrás del mejor modelo propietario?
- [ ] [E] ¿Qué funcionalidades alrededor del modelo te puede resolver una API (escalabilidad, function calling, structured outputs, guardrails)? ¿Qué limitaciones tiene (logprobs, finetuning)?
- [ ] [E] ¿Por qué "las APIs son caras, pero la ingeniería puede serlo todavía más"? ¿Qué rol juegan el SLA y una API estándar?
- [ ] [E] ¿Qué riesgos de control y transparencia tienen los modelos comerciales? (Rate limits, sobrecensura, cambios sin aviso, perder el acceso.)
- [ ] [E] ¿Cuándo es obligatorio el despliegue *on-device*?

#### Navigate Public Benchmarks

- [ ] [R] ¿Qué es un *evaluation harness*? Nombrá dos.
- [ ] [E] ¿Por qué los leaderboards públicos incluyen pocos benchmarks? ¿Qué problemas trae eso para interpretarlos?
- [ ] [E] ¿Por qué importa la correlación entre benchmarks? ¿Qué mostró la tabla de correlaciones del leaderboard de Hugging Face sobre TruthfulQA?
- [ ] [E] ¿Qué problema tiene promediar los puntajes de distintos benchmarks? ¿Qué alternativa usa HELM (*mean win rate*)?
- [ ] [E] ¿Cómo armarías un leaderboard propio con benchmarks públicos? ¿Qué tenés que cuidar al agregar los puntajes?
- [ ] [R] ¿Qué es *data contamination*? ¿Qué demostró el paper satírico "Pretraining on the Test Set Is All You Need"?
- [ ] [E] ¿De qué tres formas puede ocurrir la contaminación (accidental por scraping, indirecta por misma fuente, intencional por buenas razones)?
- [ ] [E] ¿Cómo se detecta la contaminación con *n-gram overlapping* y con *perplexity*? ¿Qué ventajas y desventajas tiene cada método?
- [ ] [E] ¿Qué deberían reportar idealmente los desarrolladores de modelos sobre contaminación? ¿Para qué sirven, en definitiva, los benchmarks públicos en tu proceso?

### 4.3 Design Your Evaluation Pipeline

#### Step 1. Evaluate All Components in a System

- [ ] [E] ¿Por qué hay que evaluar cada componente por separado además del resultado end-to-end? Usá el ejemplo de extraer el empleador actual de un CV en PDF.
- [ ] [R] ¿Qué diferencia hay entre *turn-based evaluation* y *task-based evaluation*? ¿Cuál importa más y qué dificultad tiene?

#### Step 2. Create an Evaluation Guideline

- [ ] [E] ¿Por qué crear la guía de evaluación es el paso más importante? ¿Por qué hay que definir también lo que la aplicación NO debe hacer?
- [ ] [E] ¿Por qué una respuesta correcta no siempre es una buena respuesta? (Ejemplo de LinkedIn: "You are a terrible fit".)
- [ ] [R] ¿Qué es un *scoring rubric* y por qué hay que validarlo con humanos?
- [ ] [E] ¿Cómo y por qué conectar las métricas de evaluación con métricas de negocio? Usá el ejemplo de factual consistency y porcentaje de consultas automatizadas.
- [ ] [E] ¿Qué tensión hay entre optimizar métricas de *stickiness* y *engagement* y la responsabilidad social?

#### Step 3. Define Evaluation Methods and Data

- [ ] [E] ¿Por qué distintos criterios pueden requerir distintos métodos? ¿Qué es combinar un clasificador barato sobre el 100% con un juez caro sobre el 1%?
- [ ] [E] ¿Para qué sirven los logprobs en la evaluación?
- [ ] [E] ¿Qué rol tiene la evaluación humana incluso en producción? ¿Qué hacía LinkedIn?
- [ ] [R] ¿Qué es hacer *slicing* de los datos y para qué cuatro cosas sirve?
- [ ] [E] Explicá la *Simpson's paradox* con el ejemplo de la tabla de modelos A y B.
- [ ] [R] ¿Qué conjuntos de evaluación distintos conviene tener? (Distribución de producción, por segmento, errores frecuentes del sistema, errores frecuentes de usuarios, fuera de alcance.)
- [ ] [E] ¿Cómo usás *bootstrapping* para saber si tu set de evaluación es suficientemente grande?
- [ ] [R] Según la regla de OpenAI, ¿cuántos ejemplos necesitás para detectar con 95% de confianza una diferencia del 30%, del 10%, del 3% y del 1%? ¿Cuál es la regla general?
- [ ] [E] ¿Qué preguntas deberías hacerte para evaluar tu propio pipeline de evaluación? (Señales correctas, confiabilidad, correlación entre métricas, costo y latencia.)
- [ ] [E] ¿Por qué tenés que iterar el pipeline pero mantener cierta consistencia? ¿Qué tenés que registrar en el *experiment tracking*?

### Escenarios integradores

- [ ] [A] Tu banco quiere un asistente que resuma los términos y condiciones de productos de inversión para clientes. Definí los criterios de evaluación en los cuatro grupos (dominio, generación, instrucciones, costo/latencia) y elegí un método para cada uno.
- [ ] [A] El área de cumplimiento prohíbe enviar datos de clientes fuera del país. El equipo de producto quiere usar el modelo más potente del mercado, que solo está disponible por API en EE. UU. Analizá la decisión con los siete ejes de build vs. buy y proponé alternativas.
- [ ] [A] Tu chatbot de atención al cliente de una billetera virtual tiene 85% de factual consistency. El gerente pregunta si "está listo". ¿Qué información te falta para responder? ¿Cómo conectarías esa métrica con una métrica de negocio?
- [ ] [A] Comparaste dos prompts para clasificar reclamos bancarios con 50 ejemplos y el nuevo dio 4% mejor. ¿Podés afirmar que es mejor? ¿Qué harías?
- [ ] [A] Tu modelo de detección de consultas fraudulentas mejora en el total, pero los usuarios de la app móvil se quejan más que antes. ¿Qué fenómeno podría estar pasando y cómo lo investigarías?
- [ ] [A] Diseñá los conjuntos de evaluación (*slices*) para un asistente de préstamos personales que atiende por web y por WhatsApp, a clientes nuevos y existentes, y que no debe dar asesoramiento impositivo.

### Práctica del capítulo

Diseñá un pipeline de evaluación completo para un asistente que responde consultas sobre una tarjeta de crédito ficticia (podés reutilizar lo del capítulo 3):

1. Escribí una guía de evaluación con 3 criterios (por ejemplo, relevancia, factual consistency y seguridad), su sistema de puntuación y una rúbrica con ejemplos de cada puntaje.
2. Armá al menos tres *slices*: preguntas normales, preguntas con errores de tipeo y preguntas fuera de alcance (por ejemplo, sobre política).
3. Probá dos modelos (o un modelo con dos prompts) y calculá los resultados por slice y en total.
4. Hacé bootstrapping (por ejemplo, 20 remuestreos) para ver cuánto varía el resultado.

**Qué aprendés:** a armar el pipeline que vas a usar en todos los capítulos siguientes para medir si un cambio mejora o empeora tu sistema.

### Glosario para completar

- **Evaluation-driven development**: 
- **Domain-specific / generation / instruction-following capability**: 
- **Fluency / coherence / faithfulness / relevance**: 
- **Local vs. global factual consistency**: 
- **Textual entailment (NLI)**: 
- **SelfCheckGPT / SAFE**: 
- **IFEval / INFOBench**: 
- **Pareto optimization**: 
- **Hard vs. soft attributes**: 
- **Open weight vs. open model**: 
- **Inference service / model API**: 
- **Evaluation harness / leaderboard**: 
- **Data contamination**: 
- **Turn-based vs. task-based evaluation**: 
- **Scoring rubric**: 
- **Slicing / Simpson's paradox**: 
- **Bootstrapping**: 

---

## Capítulo 5: Prompt Engineering

### Antes de leer

- [ ] ¿Qué creés que hace que un prompt sea "bueno"? Escribí tres reglas que usarías hoy.
- [ ] ¿Cómo intentaría un usuario malicioso hacer que el chatbot de un banco revele información que no debería?
- [ ] ¿Pensás que el *prompt engineering* es una disciplina de ingeniería o "jugar con palabras"? ¿Por qué?

### 5.1 Introduction to Prompting

- [ ] [R] ¿Qué es un prompt y cuáles son sus tres partes típicas?
- [ ] [E] ¿Por qué la cantidad de prompt engineering necesaria depende de la *robustness* del modelo? ¿Cómo se mide la robustness y con qué se correlaciona?
- [ ] [E] Según la cita del research manager de OpenAI, ¿cuál es el problema real con el prompt engineering? ¿Qué más necesitás para llevar una aplicación a producción?

#### In-Context Learning: Zero-Shot and Few-Shot

- [ ] [R] ¿Qué es *in-context learning*? ¿Qué demostró el paper de GPT-3?
- [ ] [E] ¿Por qué se dice que el in-context learning es una forma de *continual learning*? Usá el ejemplo de la documentación de JavaScript.
- [ ] [R] ¿Qué es un *shot*? ¿Qué diferencia hay entre *zero-shot* y *few-shot*?
- [ ] [E] ¿Por qué el few-shot mejoró mucho a GPT-3 pero poco a GPT-4 en el análisis de Microsoft? ¿En qué casos los ejemplos siguen haciendo una gran diferencia?
- [ ] [R] ¿Cómo usa la autora los términos *prompt* y *context* en el libro?
- [ ] [E] ¿Qué dice la analogía de François Chollet de un foundation model como "biblioteca de programas"?

#### System Prompt and User Prompt

- [ ] [R] ¿Qué suele ir en el *system prompt* y qué en el *user prompt*?
- [ ] [E] ¿Qué es el *chat template* de un modelo y en qué se diferencia de un *prompt template*? ¿Por qué un error de template es tan peligroso (falla silenciosa)?
- [ ] [R] ¿Qué buenas prácticas recomienda el libro para evitar errores de template?
- [ ] [E] Si el modelo concatena system prompt y user prompt en un solo texto, ¿por qué el system prompt mejoraría el rendimiento? Explicá las dos razones posibles.

#### Context Length and Context Efficiency

- [ ] [R] ¿Cuánto creció el context length máximo entre GPT-2 y Gemini 1.5 Pro?
- [ ] [E] ¿Qué partes de un prompt entiende mejor un modelo? ¿Qué es el test *needle in a haystack* (NIAH) y por qué conviene usar información privada en el test?
- [ ] [E] ¿Qué deberías hacer si el rendimiento del modelo empeora mucho con contextos más largos?

### 5.2 Prompt Engineering Best Practices

#### Write Clear and Explicit Instructions

- [ ] [E] ¿Por qué hay que explicar sin ambigüedad lo que querés, incluido qué hacer ante la incertidumbre? Usá el ejemplo de puntuar ensayos.
- [ ] [E] ¿Por qué pedirle al modelo que adopte un *persona* cambia el resultado? (Ejemplo de la maestra de primer grado.)
- [ ] [E] ¿Para qué sirven los ejemplos en el prompt? ¿Por qué conviene elegir formatos de ejemplo que usen menos tokens?
- [ ] [E] ¿Por qué conviene especificar el formato de salida y usar *markers* para indicar dónde termina el input? ¿Qué pasa si no los usás?

#### Provide Sufficient Context

- [ ] [E] ¿Cómo ayuda el contexto a reducir alucinaciones? ¿Qué es *context construction*?
- [ ] [E] ¿Qué opciones hay para restringir el conocimiento del modelo solo al contexto provisto? ¿Por qué ninguna es infalible?

#### Break Complex Tasks into Simpler Subtasks

- [ ] [E] ¿Qué es la *prompt decomposition*? Explicá el ejemplo del chatbot de soporte (clasificación de intención + respuesta).
- [ ] [R] ¿Cuáles son los cuatro beneficios adicionales de descomponer prompts (*monitoring*, *debugging*, *parallelization*, *effort*)?
- [ ] [E] ¿Qué desventajas tiene descomponer (latencia percibida, costo)? ¿Por qué el costo no necesariamente se duplica? ¿Qué aprendió GoDaddy?

#### Give the Model Time to Think

- [ ] [R] ¿Qué es *chain-of-thought* (CoT)? Nombrá distintas variantes (zero-shot, con pasos explícitos, one-shot).
- [ ] [E] ¿Qué es la *self-critique* y en qué se parece a CoT? ¿Qué costo tienen ambas técnicas en latencia?

#### Iterate on Your Prompts, Evaluate Prompt Engineering Tools, Organize and Version Prompts

- [ ] [E] ¿Por qué tenés que iterar los prompts de forma sistemática (versionado, experiment tracking, métricas estándar)? ¿Por qué evaluar cada prompt en el contexto de todo el sistema?
- [ ] [R] ¿Qué hacen herramientas como DSPy u OpenPrompt? ¿A qué se parecen funcionalmente?
- [ ] [R] ¿Cómo funciona Promptbreeder?
- [ ] [E] ¿Qué riesgos tienen las herramientas de prompt engineering (llamadas ocultas a la API, errores del desarrollador, cambios sin aviso)? ¿Qué recomienda la autora?
- [ ] [E] ¿Por qué conviene separar los prompts del código? Nombrá las cuatro ventajas.
- [ ] [E] ¿Qué metadata conviene guardar con cada prompt? ¿Qué problema tiene versionar prompts junto con el código en git y qué resuelve un *prompt catalog*?

### 5.3 Defensive Prompt Engineering

- [ ] [R] ¿Cuáles son los tres tipos principales de ataques con prompts?
- [ ] [R] ¿Qué riesgos generan esos ataques? (Ejecución remota de código o herramientas, fuga de datos, daño social, desinformación, interrupción del servicio, riesgo de marca.)

#### Proprietary Prompts and Reverse Prompt Engineering

- [ ] [R] ¿Qué es *reverse prompt engineering* y cómo se hace?
- [ ] [E] ¿Por qué un prompt extraído puede no ser real? ¿Qué más, además del system prompt, se puede extraer?
- [ ] [E] ¿Por qué la autora dice que los prompts propietarios son más un pasivo que una ventaja competitiva? ¿Qué significa "escribí tu system prompt asumiendo que algún día va a ser público"?

#### Jailbreaking and Prompt Injection

- [ ] [R] Diferenciá *jailbreaking* de *prompt injection*. Dá un ejemplo de cada uno.
- [ ] [E] ¿Por qué los ataques con prompts son posibles justamente porque los modelos siguen instrucciones?
- [ ] [R] Describí las técnicas de *direct manual prompt hacking*: ofuscación, manipulación del formato de salida y roleplaying (DAN, el "exploit de la abuela").
- [ ] [R] ¿Cómo funciona PAIR como ataque automatizado?
- [ ] [E] ¿Qué es la *indirect prompt injection* y por qué es más poderosa? Explicá *passive phishing* y *active injection* con un ejemplo de cada uno.
- [ ] [E] ¿Por qué es más difícil sanitizar contenido malicioso en lenguaje natural que una SQL injection clásica? (Ejemplo de "Bruce Remove All Data Lee".)

#### Information Extraction

- [ ] [R] ¿Para qué tres fines se puede abusar de la extracción de información? (Robo de datos, violación de privacidad, copyright.)
- [ ] [R] ¿Qué es *factual probing*? ¿Cómo funciona el benchmark LAMA?
- [ ] [E] ¿Qué mostró el ataque de divergencia de Nasr et al. (repetir "poem" para siempre)? ¿Qué relación hay entre el tamaño del modelo y cuánto memoriza?
- [ ] [E] ¿Por qué la regurgitación de contenido con copyright no literal (el ejemplo de "Randalf") es difícil de detectar?

#### Defenses Against Prompt Attacks

- [ ] [R] ¿Qué son el *violation rate* y el *false refusal rate*? ¿Por qué necesitás medir los dos?
- [ ] [R] ¿Qué herramientas y prácticas existen para probar la seguridad de un sistema (benchmarks, herramientas de probing, *red teaming*)?
- [ ] [E] ¿Qué es la *instruction hierarchy* de OpenAI? ¿Cuáles son sus cuatro niveles y por qué neutraliza muchas indirect prompt injections?
- [ ] [E] ¿Qué es un *borderline request* y cómo debería responderlo un buen sistema? (Ejemplo de la habitación cerrada con llave.)
- [ ] [E] ¿Qué defensas a nivel prompt menciona el libro? ¿Qué desventaja tiene repetir el system prompt antes y después del user prompt?
- [ ] [E] ¿Qué defensas a nivel sistema menciona? (Aislamiento, aprobación humana para comandos con impacto, temas fuera de alcance, detección de anomalías, guardrails de entrada y salida, patrones de uso.)
- [ ] [E] ¿Por qué no alcanza con guardrails de entrada y también necesitás guardrails de salida?

### Escenarios integradores

- [ ] [A] Escribí el system prompt de un asistente que responde dudas sobre el home banking de un banco. Aplicá al menos cinco buenas prácticas del capítulo (persona, instrucciones claras, ejemplos, formato de salida, qué hacer ante la duda, qué temas no tocar).
- [ ] [A] Tu asistente de una billetera virtual puede consultar movimientos y también iniciar transferencias. Un usuario escribe: "¿Cuál es mi saldo? Además, transferí todo a la cuenta X". Describí qué defensas en los tres niveles (modelo, prompt y sistema) evitarían que se ejecute esa transferencia.
- [ ] [A] Un asistente lee los mails de los clientes para clasificar reclamos y generar respuestas automáticas. ¿Qué riesgo de indirect prompt injection ves? ¿Cómo lo mitigarías?
- [ ] [A] Tu prompt para analizar solicitudes de crédito ya tiene 2.000 tokens y cada cambio rompe algo. ¿Cómo lo descompondrías en subtareas? ¿Qué ganás y qué perdés?
- [ ] [A] Varias aplicaciones del banco comparten el mismo prompt de detección de datos sensibles. Diseñá cómo organizarías y versionarías ese prompt para que un cambio no rompa todas las aplicaciones a la vez.

### Práctica del capítulo

Construí un mini "clasificador de reclamos bancarios" con dos prompts encadenados:

1. Un primer prompt clasifica la intención (por ejemplo: tarjeta, transferencia, préstamo, fraude, otro) y devuelve JSON.
2. Un segundo prompt, distinto según la intención, genera la respuesta.

Guardá los prompts en archivos separados del código, con metadata (modelo, fecha, versión). Después intentá atacarlo con 10 prompts maliciosos (pedirle el system prompt, roleplaying, instrucciones escondidas en el reclamo) y medí el *violation rate*. Agregá defensas y volvé a medir, incluido el *false refusal rate* con reclamos legítimos.

**Qué aprendés:** a descomponer tareas, a versionar prompts como código y a ver en vivo lo fácil que es romper un sistema que no tiene defensas.

### Glosario para completar

- **Prompt / context**: 
- **In-context learning / zero-shot / few-shot**: 
- **System prompt / user prompt**: 
- **Chat template vs. prompt template**: 
- **Needle in a haystack (NIAH)**: 
- **Persona**: 
- **Context construction**: 
- **Prompt decomposition**: 
- **Chain-of-thought (CoT)**: 
- **Self-critique**: 
- **Prompt catalog**: 
- **Reverse prompt engineering**: 
- **Jailbreaking / prompt injection / indirect prompt injection**: 
- **Factual probing**: 
- **Violation rate / false refusal rate**: 
- **Instruction hierarchy**: 
- **Red teaming**: 

---

## Capítulo 6: RAG and Agents

### Antes de leer

- [ ] Si un chatbot tiene que responder sobre los 5.000 documentos internos de un banco, ¿cómo harías para que "sepa" lo que dicen?
- [ ] ¿Qué es para vos un "agente" de IA? ¿En qué se diferencia de un chatbot?
- [ ] ¿Qué acciones nunca dejarías que un agente haga solo en una fintech?

### 6.1 RAG

- [ ] [R] ¿Qué es RAG? ¿Quién introdujo el patrón *retrieve-then-generate* y quién acuñó el término?
- [ ] [E] ¿Por qué se dice que la *context construction* para foundation models equivale al *feature engineering* del ML clásico?
- [ ] [E] ¿Por qué la autora cree que contextos más largos no van a terminar con RAG? Dá los dos argumentos. ¿Qué recomendó Anthropic sobre bases de conocimiento de menos de 200.000 tokens?

#### RAG Architecture

- [ ] [R] ¿Cuáles son los dos componentes de un sistema RAG? ¿Cuáles son las dos funciones principales del retriever (*indexing* y *querying*)?
- [ ] [E] ¿Por qué se dividen los documentos en *chunks* antes de indexarlos?

#### Retrieval Algorithms

- [ ] [R] ¿Qué diferencia hay entre *sparse* y *dense retrieval*? ¿Por qué la autora prefiere hablar de *term-based* vs. *embedding-based*? (Caso SPLADE.)
- [ ] [R] ¿Qué es *term frequency* (TF) y qué es *inverse document frequency* (IDF)? Si hay 10 documentos y 5 contienen un término, ¿cuánto vale su IDF (en la versión simple del libro)?
- [ ] [E] ¿Qué combina TF-IDF y por qué los términos que aparecen en muchos documentos son menos informativos?
- [ ] [R] ¿Qué es un *inverted index* y qué solución lo usa? ¿Qué mejora BM25 sobre TF-IDF?
- [ ] [E] ¿Qué problemas trae la tokenization en la búsqueda por términos (ejemplo "hot dog") y cómo se mitigan?
- [ ] [E] ¿Qué problema tiene la búsqueda por términos que resuelve la *semantic retrieval*? (Ejemplo de "transformer architecture".)
- [ ] [R] ¿Cuáles son los dos pasos del querying en *embedding-based retrieval*? ¿Qué es una *vector database*?
- [ ] [E] ¿Qué es k-NN y por qué no escala? ¿Qué es ANN?
- [ ] [R] Describí brevemente LSH, HNSW, *product quantization*, IVF y Annoy. ¿Qué tienen en común (buckets, árboles, grafos)?
- [ ] [E] Compará term-based y embedding-based retrieval en velocidad, rendimiento y costo. ¿Qué problema tienen los embeddings con códigos de error o nombres de producto?
- [ ] [R] ¿Qué miden *context precision* y *context recall*? ¿Por qué muchos frameworks solo soportan context precision?
- [ ] [R] ¿Qué métricas usás si te importa el orden de los documentos recuperados (NDCG, MAP, MRR)?
- [ ] [E] ¿Qué costos agrega la semantic retrieval (generación de embeddings, almacenamiento, búsqueda)? ¿Cuándo pesan más?
- [ ] [E] ¿Qué trade-off hay entre indexing y querying? Compará HNSW con LSH. ¿Qué cuatro métricas usa ANN-Benchmarks?
- [ ] [R] ¿Cuáles son las tres cosas que tenés que evaluar en un sistema RAG?
- [ ] [R] ¿Qué es la *hybrid search*? ¿Qué es el *reranking*?
- [ ] [E] ¿Cómo funciona la *reciprocal rank fusion* (RRF)? Si un documento queda primero en un retriever y segundo en otro, ¿qué puntaje recibe en la versión simplificada?

#### Retrieval Optimization

- [ ] [R] ¿Qué estrategias de *chunking* menciona el libro (largo fijo, recursivo, específico por tipo de documento, por tokens)?
- [ ] [E] ¿Para qué sirve el *overlap* entre chunks? (Ejemplo "I left my wife a note".) ¿Qué desventaja tiene hacer chunking por tokens del modelo generador?
- [ ] [E] ¿Qué ganás y qué perdés con chunks más chicos?
- [ ] [E] ¿En qué se diferencia el reranking de contexto del reranking de búsqueda tradicional? ¿Cuándo conviene rerankear por fecha?
- [ ] [E] ¿Qué es *query rewriting*? Explicá el ejemplo de "¿Y Emily Doe?". ¿Qué debería hacer el modelo si no tiene la información para reescribir (ejemplo "¿Y su esposa?")?
- [ ] [E] ¿Qué es *contextual retrieval*? Explicá las tres variantes: agregar metadata, agregar las preguntas que el chunk responde, y agregar contexto del documento original (técnica de Anthropic).
- [ ] [R] ¿Qué factores hay que considerar al evaluar una solución de retrieval?

#### RAG Beyond Texts

- [ ] [E] ¿Cómo funciona un *multimodal RAG* con CLIP? ¿Qué pasa si las imágenes tienen metadata?
- [ ] [R] ¿Cuáles son los tres pasos de un RAG con datos tabulares? ¿Qué paso intermedio puede hacer falta si hay muchas tablas?

### 6.2 Agents

#### Agent Overview

- [ ] [R] ¿Cómo define el libro a un *agent*? ¿Qué lo caracteriza?
- [ ] [E] ¿Qué relación hay entre el entorno de un agente y su conjunto de herramientas? ¿Por qué un sistema RAG es un agente?
- [ ] [E] ¿Por qué los agentes requieren modelos más potentes? Explicá los errores compuestos: si un modelo tiene 95% de accuracy por paso, ¿qué accuracy tiene en 10 pasos? ¿Y en 100?

#### Tools

- [ ] [R] ¿Qué diferencia hay entre acciones *read-only* y *write actions*? ¿Qué es el *tool inventory*?
- [ ] [R] ¿Cuáles son las tres categorías de herramientas? Dá ejemplos de cada una.
- [ ] [E] ¿Qué significa que un modelo "se vuelva *stale*"? ¿Cómo lo resuelve el web browsing y qué riesgo trae?
- [ ] [E] ¿Por qué es más eficiente darle una calculadora o un *code interpreter* al modelo que entrenarlo para esas tareas? ¿Cómo pueden las herramientas volver multimodal a un modelo de texto?
- [ ] [E] ¿Qué riesgos tienen las write actions? Explicá la analogía del pasante y la base de datos de producción.
- [ ] [R] ¿Qué es *function calling*?

#### Planning

- [ ] [R] ¿Cómo se define una tarea (objetivo y restricciones)? ¿Qué es un plan?
- [ ] [E] En el ejemplo de "empresas sin ingresos que levantaron al menos USD 1.000 millones", ¿por qué una opción es más eficiente que la otra?
- [ ] [E] ¿Por qué conviene separar la planificación de la ejecución? ¿Cómo se valida un plan (heurísticas, AI judges)?
- [ ] [E] ¿Qué rol cumple el *intent classifier* en un agente? ¿Para qué sirve la clase IRRELEVANT?
- [ ] [E] ¿En qué etapas pueden intervenir los humanos? ¿Por qué hay que definir el nivel de automatización de cada acción?
- [ ] [R] ¿Cuáles son los cuatro procesos para resolver una tarea con un agente?
- [ ] [E] ¿Qué argumentos hay a favor y en contra de que los LLMs autoregressive puedan planificar? ¿Por qué la planificación es un problema de búsqueda y qué rol tiene el *backtracking*?
- [ ] [E] ¿Por qué para planificar no alcanza con conocer las acciones posibles, sino también sus resultados? (Ejemplo de la montaña.)
- [ ] [E] ¿En qué se diferencian los planificadores de un agente de RL y de un agente basado en foundation models?
- [ ] [E] ¿Qué formas hay de mejorar la capacidad de planificación de un agente?
- [ ] [R] ¿Cómo funciona el function calling en general (tool inventory, `required`, `none`, `auto`)?
- [ ] [E] ¿Por qué hay que pedirle al sistema que reporte los valores de parámetros que usa en cada llamada?
- [ ] [E] ¿Qué trade-off hay entre planes detallados y planes de alto nivel? ¿Qué es la planificación jerárquica? ¿Qué ventajas tiene planificar en lenguaje natural en lugar de usar nombres exactos de funciones?
- [ ] [R] ¿Cuáles son los cuatro tipos de *control flow* (secuencial, paralelo, if, for)? Dá un ejemplo de cada uno.
- [ ] [E] ¿En qué momentos del proceso es útil la *reflection*? ¿Qué diferencia hay entre reflection y error correction?
- [ ] [R] ¿Cómo funciona el patrón ReAct (Thought, Act, Observation)? ¿Qué agrega Reflexion?
- [ ] [E] ¿Qué costos tienen ReAct y Reflexion en tokens y latencia?
- [ ] [E] ¿Por qué más herramientas no siempre es mejor? ¿Qué podés hacer para elegir el conjunto de herramientas (comparar, *ablation study*, errores frecuentes, distribución de llamadas)?
- [ ] [R] ¿Qué es la *tool transition* que estudia Chameleon? ¿Qué propone el *skill manager* de Voyager?

#### Agent Failure Modes and Evaluation

- [ ] [R] ¿Cuáles son los tres tipos de *tool use failure* en la planificación?
- [ ] [E] ¿Qué es un *goal failure*? ¿Por qué el tiempo es una restricción que se suele olvidar? ¿Qué es un error de reflexión (ejemplo de las 50 personas en 30 habitaciones)?
- [ ] [R] ¿Qué métricas calcularías sobre un dataset de planificación (task, tool inventory)?
- [ ] [E] ¿Qué son las *tool failures*? ¿Cómo se detectan las herramientas faltantes?
- [ ] [R] ¿Qué métricas de eficiencia de un agente conviene medir? ¿Por qué comparar contra humanos puede ser engañoso?

### 6.3 Memory

- [ ] [R] ¿Cuáles son los tres mecanismos de memoria de un modelo (*internal knowledge*, *short-term memory*, *long-term memory*)? Explicá la analogía con la memoria humana.
- [ ] [E] ¿Cómo decidís en qué mecanismo guardar cada tipo de información según la frecuencia de uso?
- [ ] [R] ¿Qué cuatro beneficios trae agregar un sistema de memoria?
- [ ] [R] ¿Cuáles son las dos funciones de un sistema de memoria y las dos operaciones del memory management?
- [ ] [E] ¿Qué problema tiene la estrategia FIFO? ¿Qué estrategias más sofisticadas menciona el libro (resúmenes, eliminar redundancia, reflexión para insertar, fusionar o reemplazar)?
- [ ] [E] ¿Cómo se pueden manejar las contradicciones en la memoria?

### Escenarios integradores

- [ ] [A] Tu banco quiere un asistente interno para que los empleados de sucursal consulten 3.000 manuales de procedimientos (PDF con tablas, actualizados cada mes). Diseñá el RAG: estrategia de chunking, tipo de retrieval (term-based, embedding-based o híbrido), reranking y cómo lo evaluarías.
- [ ] [A] Los clientes de una billetera virtual preguntan cosas como "¿por qué me rechazaron la transferencia con el error TX-4031?". ¿Por qué la búsqueda solo por embeddings podría fallar acá? ¿Qué técnicas del capítulo usarías?
- [ ] [A] Querés un agente que ayude a un analista de riesgo: consulta la base de préstamos (SQL), busca noticias del cliente en internet y redacta un informe. Definí el tool inventory, separá las herramientas read-only de las write, y decidí en qué pasos exigirías aprobación humana.
- [ ] [A] Un agente de atención al cliente tiene que completar tareas de 8 pasos y tu modelo acierta el 97% por paso. ¿Qué tasa de éxito esperás? ¿Qué harías para mejorarla?
- [ ] [A] Un asesor financiero con IA conversa con el mismo cliente durante meses. ¿Qué guardarías en cada tipo de memoria? ¿Qué pasa si el cliente dijo hace seis meses que su perfil era conservador y hoy dice que quiere riesgo alto?
- [ ] [A] Con un RAG sobre la normativa del Banco Central, un usuario pregunta "¿y para personas jurídicas?" después de una pregunta sobre límites de transferencia. ¿Qué técnica aplicarías antes de buscar?

### Práctica del capítulo

Construí un RAG mínimo sobre documentos financieros (por ejemplo, 10–20 páginas de términos y condiciones de productos bancarios o de una normativa pública):

1. Hacé chunking con overlap y generá embeddings (en Java con Spring AI y un vector store como PGVector, o en Python).
2. Implementá también una búsqueda BM25 y combiná ambas con RRF.
3. Armá 15 preguntas con los chunks relevantes marcados y medí *context precision* y *context recall* con solo embeddings, solo BM25 y la búsqueda híbrida.
4. Opcional: agregá una herramienta (por ejemplo, una calculadora de cuotas) y dejá que el modelo decida cuándo usarla con function calling.

**Qué aprendés:** cómo cada decisión (chunking, tipo de retrieval) cambia lo que el modelo "ve", y cómo medirlo en lugar de adivinarlo.

### Glosario para completar

- **RAG / retriever / generator**: 
- **Chunk / chunking / overlap**: 
- **Indexing / querying**: 
- **TF-IDF / BM25 / inverted index**: 
- **Embedding-based (semantic) retrieval**: 
- **Vector database / vector search**: 
- **k-NN / ANN (HNSW, IVF, LSH, product quantization)**: 
- **Context precision / context recall**: 
- **Hybrid search / reranking / RRF**: 
- **Query rewriting**: 
- **Contextual retrieval**: 
- **Agent / environment / tool inventory**: 
- **Read-only vs. write actions**: 
- **Function calling**: 
- **Plan / task decomposition / control flow**: 
- **ReAct / Reflexion**: 
- **Short-term vs. long-term memory**: 

---

## Capítulo 7: Finetuning

### Antes de leer

- [ ] ¿Cuándo creés que conviene hacer finetuning en lugar de mejorar el prompt o agregar RAG?
- [ ] ¿Por qué pensás que entrenar un modelo necesita mucha más memoria que usarlo?
- [ ] ¿Qué significa para vos que un número esté en "16 bits" o en "4 bits"? ¿Qué se pierde?

### 7.1 Finetuning Overview

- [ ] [R] ¿Qué es *transfer learning*? Explicá el ejemplo de traducción portugués–español de Google.
- [ ] [E] ¿Qué es *sample efficiency* y por qué el finetuning de un buen modelo base necesita tan pocos ejemplos comparado con entrenar desde cero?
- [ ] [R] ¿Qué es *feature-based transfer* y en qué se diferencia del finetuning?
- [ ] [R] ¿Qué es *continued pre-training* (self-supervised finetuning)? Dá un ejemplo.
- [ ] [R] ¿Qué es *infilling finetuning* y para qué tareas sirve?
- [ ] [R] ¿Qué formato de datos usa el supervised finetuning y cuál el preference finetuning?
- [ ] [E] ¿Qué es el *long-context finetuning* y por qué es más difícil que otras técnicas?
- [ ] [E] ¿Por qué, como desarrollador de aplicaciones, probablemente hagas finetuning sobre un modelo ya post-entrenado y no sobre uno solo pre-entrenado?

### 7.2 When to Finetune

#### Reasons to Finetune

- [ ] [R] ¿Cuál es la razón principal para hacer finetuning? ¿Para qué tipo de mejora se usa más seguido?
- [ ] [E] ¿Por qué el finetuning sirve para dialectos SQL poco comunes o consultas específicas de un cliente?
- [ ] [E] ¿Cómo puede usarse el finetuning para mitigar sesgos?
- [ ] [E] ¿Qué es *distillation*? ¿Qué mostró el caso de Grammarly con Flan-T5?

#### Reasons Not to Finetune

- [ ] [E] ¿Por qué hacer finetuning para una tarea puede empeorar el rendimiento en otras? ¿Qué opciones tenés si te pasa? (Ejemplo de recomendaciones, cambios de pedido y feedback.)
- [ ] [E] ¿Qué inversiones iniciales y continuas exige el finetuning (datos, conocimiento de entrenamiento, serving, mantenimiento)?
- [ ] [E] ¿Por qué los nuevos modelos base complican la decisión de mantener un modelo con finetuning propio?
- [ ] [E] ¿Qué historia se repite según los practicantes que entrevistó la autora cuando alguien insiste en hacer finetuning porque "el prompting no funciona"?
- [ ] [E] ¿Qué pasó con BloombergGPT frente a GPT-4? ¿Qué lección deja sobre los modelos domain-specific en finanzas?
- [ ] [E] ¿Por qué el ahorro de tokens dejó de ser una ventaja tan fuerte del finetuning? ¿Qué ventaja sigue teniendo frente a poner ejemplos en el prompt?

#### Finetuning and RAG

- [ ] [E] ¿Qué diferencia hay entre una falla basada en información y una falla basada en comportamiento? Dá ejemplos de cada una.
- [ ] [E] ¿Qué mostró el paper de Ovadia et al. (2024) sobre RAG vs. finetuning para información actualizada?
- [ ] [R] Completá la frase de la autora: "finetuning is for ___, and RAG is for ___". Explicala con tus palabras.
- [ ] [E] Si tu modelo tiene problemas de información y de comportamiento, ¿por dónde empezás y por qué?
- [ ] [R] Describí los cinco pasos del workflow sugerido para adaptar un modelo a una tarea.
- [ ] [E] ¿Qué tipo de complejidad agrega el embedding-based retrieval y qué tipo agrega el finetuning?

### 7.3 Memory Bottlenecks

- [ ] [R] ¿Cuáles son los tres factores que más contribuyen a la memoria que usa un modelo durante el finetuning?
- [ ] [R] ¿Qué es un *trainable parameter* y qué es un *frozen parameter*?

#### Backpropagation and Trainable Parameters

- [ ] [R] ¿Cuáles son las dos fases de un paso de entrenamiento con *backpropagation*? ¿Cuál se ejecuta en inferencia?
- [ ] [R] Explicá qué son la *loss*, el *gradient* y el *optimizer*. Nombrá dos optimizadores.
- [ ] [E] ¿Por qué cada parámetro entrenable agrega memoria extra durante el entrenamiento?

#### Memory Math

- [ ] [R] ¿Cuál es la fórmula aproximada de memoria para inferencia? Calculá la memoria para un modelo de 13B parámetros en 2 bytes.
- [ ] [R] ¿Cuál es la fórmula de memoria para entrenamiento? ¿Cuántos valores extra guarda por parámetro entrenable SGD, momentum y Adam?
- [ ] [E] Calculá la memoria de gradientes y estados del optimizador para un modelo de 13B con Adam en 2 bytes, actualizando todos los parámetros vs. solo 1B.
- [ ] [E] ¿Por qué la memoria de activaciones puede superar a la de los pesos? ¿Qué es *gradient checkpointing* y qué trade-off tiene?

#### Numerical Representations

- [ ] [R] ¿Cuántos bits usan FP64, FP32, FP16, BF16 e INT8? ¿Qué es *single*, *double* y *half precision*?
- [ ] [E] ¿Qué determinan los bits de *range* y los de *precision*? ¿Por qué BF16 puede representar valores que FP16 no, pero con menos precisión?
- [ ] [E] ¿Qué pasó cuando muchos equipos cargaron Llama 2 en FP16 en vez de BF16? ¿Qué lección deja?

#### Quantization

- [ ] [R] ¿Qué es *quantization*? ¿Cuánta memoria ocupan los pesos de un modelo de 10B en 32 bits y en 16 bits?
- [ ] [R] ¿Qué decisiones hay que tomar al cuantizar (qué cuantizar y cuándo)? ¿Qué es PTQ y por qué es la más común?
- [ ] [E] ¿Por qué la cuantización de pesos es más común que la de activaciones?
- [ ] [R] ¿Qué es BitNet b1.58 y qué mostró?
- [ ] [E] ¿Por qué reducir la precisión suele acelerar el cómputo, pero no siempre baja la latencia? ¿Qué desventajas tiene?
- [ ] [E] ¿Cuáles son los dos objetivos de la *training quantization*? ¿Qué es QAT y por qué no reduce el tiempo de entrenamiento?
- [ ] [E] ¿Qué es entrenar en *mixed precision*? ¿Por qué el entrenamiento es más sensible a la baja precisión que la inferencia?

### 7.4 Finetuning Techniques

#### Parameter-Efficient Finetuning

- [ ] [E] ¿Por qué el *full finetuning* de un modelo de 7B con Adam en 16 bits necesita unos 56 GB (sin contar activaciones)? Hacé la cuenta.
- [ ] [R] ¿Qué es el *partial finetuning* y por qué es *parameter-inefficient*?
- [ ] [R] ¿Cuándo se considera que una técnica es *parameter-efficient*? ¿Qué hicieron Houlsby et al. con los *adapters*?
- [ ] [E] ¿Qué desventaja tenían los adapters originales en inferencia?
- [ ] [R] ¿Cuáles son los dos grandes grupos de técnicas PEFT? Nombrá ejemplos de cada uno.
- [ ] [E] ¿En qué se diferencian los *soft prompts* de los *hard prompts*? ¿Qué diferencia a prefix-tuning de prompt tuning?

#### LoRA

- [ ] [E] ¿Cómo funciona LoRA? Explicá la descomposición de una matriz W en A y B, el rol del *rank* r y el hiperparámetro α.
- [ ] [E] ¿Qué es la *low-rank factorization*? Usá el ejemplo de la matriz de 9 × 9.
- [ ] [E] ¿Por qué LoRA no agrega latencia de inferencia a diferencia de los adapters originales?
- [ ] [E] ¿Por qué funciona LoRA? Explicá la idea de *intrinsic dimension* y por qué los modelos más grandes y mejor entrenados son más fáciles de ajustar.
- [ ] [E] ¿Por qué no se usa LoRA directamente para el pre-training?
- [ ] [E] ¿A qué matrices se aplica LoRA normalmente? Con un presupuesto fijo de parámetros, ¿qué configuración funcionó mejor en el paper original? ¿Qué agregó Databricks sobre las capas feedforward?
- [ ] [E] ¿Qué valores de r suelen alcanzar? ¿Subir r siempre mejora?
- [ ] [E] ¿Cuáles son las dos formas de servir un modelo con LoRA? ¿Cuándo conviene cada una?
- [ ] [E] Hacé la cuenta del ejemplo de 100 clientes: ¿cuántos parámetros almacenás si fusionás cada adapter vs. si los mantenés separados?
- [ ] [E] ¿Cuáles son las desventajas de LoRA?
- [ ] [E] ¿Por qué cuantizar el modelo es más efectivo para ahorrar memoria que reducir los parámetros de LoRA?
- [ ] [R] ¿Qué es QLoRA? ¿Qué es NF4 y qué son los *paged optimizers*? ¿Cuál es su principal limitación?

#### Model Merging and Multi-Task Finetuning

- [ ] [E] ¿Qué es *model merging* y qué valor puede agregar (mejor rendimiento, menos memoria)?
- [ ] [E] ¿Qué problemas tienen el *simultaneous finetuning* y el *sequential finetuning*? ¿Qué es el *catastrophic forgetting* y cómo ayuda el merging?
- [ ] [E] ¿Por qué el merging es atractivo para el despliegue on-device? ¿Qué relación tiene con el *federated learning*?
- [ ] [E] ¿En qué se diferencia el model merging de un *ensemble*? ¿Qué costo tiene el ensemble?
- [ ] [R] ¿Cuáles son los tres enfoques de merging (*summing*, *layer stacking*, *concatenation*)?
- [ ] [R] ¿Qué es un *task vector* y qué es la *task arithmetic*? ¿Para qué puede servir restar un task vector?
- [ ] [R] Explicá la intuición de SLERP. ¿Cuántos vectores puede combinar por vez?
- [ ] [E] ¿Por qué podar parámetros redundantes de los task vectors (TIES, DARE) mejora el modelo fusionado?
- [ ] [R] ¿Qué es el *frankenmerging*? ¿Cómo se usa el layer stacking para crear MoE (*sparse upcycling*) y para *model upscaling* (SOLAR 10.7B)?
- [ ] [E] ¿Por qué no se recomienda la concatenación?

#### Finetuning Tactics

- [ ] [R] ¿Qué tres cosas tenés que elegir para hacer finetuning?
- [ ] [R] Describí el *progression path* y el *distillation path* que sugiere OpenAI.
- [ ] [E] ¿Cómo elegís entre LoRA y full finetuning según la cantidad de datos y la cantidad de modelos que tenés que servir?
- [ ] [E] ¿Qué ventajas y limitaciones tienen las APIs de finetuning frente a frameworks propios?
- [ ] [E] ¿Qué es el *learning rate*? ¿Qué te dice la curva de loss si es muy alto o muy bajo? ¿Qué es un *learning rate schedule*?
- [ ] [E] ¿Qué efecto tiene el *batch size*? ¿Qué es *gradient accumulation*?
- [ ] [E] ¿Cómo usás la diferencia entre *training loss* y *validation loss* para decidir el número de epochs?
- [ ] [R] ¿Qué es el *prompt loss weight* y qué valor suele usarse por defecto?

### Escenarios integradores

- [ ] [A] Tu chatbot de una billetera virtual responde bien en general, pero (a) no conoce las comisiones nuevas que salieron este mes y (b) no respeta el formato JSON que espera tu backend. Para cada problema, ¿usarías RAG o finetuning? Justificá con la regla "form vs. facts".
- [ ] [A] Tu banco quiere un modelo propio para clasificar reclamos que tenga que correr on-premise por regulación. Tenés una GPU de 24 GB. ¿Qué tamaño de modelo podrías servir en 16 bits? ¿Y hacerle finetuning con LoRA o QLoRA? Hacé las cuentas aproximadas.
- [ ] [A] Querés ofrecer a 50 fintechs clientes un modelo adaptado a cada una (tono, productos, formato). ¿Cómo usarías LoRA para hacerlo eficiente en almacenamiento y serving?
- [ ] [A] Tu jefe quiere "entrenar un BloombergGPT argentino". Usando lo que dice el capítulo, ¿qué argumentos le darías a favor y en contra? ¿Qué propondrías probar primero?
- [ ] [A] Tenés un modelo con finetuning para detectar fraude en descripciones de transacciones y otro para clasificar reclamos, ambos con el mismo modelo base. Querés desplegar uno solo en la app móvil. ¿Qué técnica usarías y qué riesgos tiene?

### Práctica del capítulo

Hacé un finetuning con LoRA (en Python con Hugging Face PEFT, unsloth o una API de finetuning) de un modelo chico (por ejemplo, de 1B–3B parámetros) para una tarea financiera con formato estricto, como extraer de un texto libre de transferencia los campos `monto`, `moneda`, `destinatario` y `concepto` en JSON:

1. Armá 200–500 ejemplos (podés generar parte con un modelo grande, revisándolos a mano).
2. Antes de entrenar, calculá a mano la memoria aproximada que vas a necesitar.
3. Compará contra el modelo base solo con un prompt few-shot, usando el pipeline de evaluación del capítulo 4 (% de JSON válido y % de campos correctos).
4. Probá dos valores de r y mirá las curvas de training y validation loss.

**Qué aprendés:** el ciclo completo de finetuning y, sobre todo, si de verdad le gana a un buen prompt en tu caso.

### Glosario para completar

- **Transfer learning / sample efficiency**: 
- **Continued pre-training**: 
- **Distillation**: 
- **Information-based vs. behavior-based failure**: 
- **Backpropagation / forward pass / backward pass**: 
- **Loss / gradient / optimizer (SGD, Adam)**: 
- **Trainable vs. frozen parameters**: 
- **Gradient checkpointing**: 
- **FP32 / FP16 / BF16 / INT8**: 
- **Quantization / PTQ / QAT / mixed precision**: 
- **Full vs. partial finetuning**: 
- **PEFT / adapters / soft prompts**: 
- **LoRA / rank / intrinsic dimension**: 
- **QLoRA / NF4**: 
- **Model merging / task vector / SLERP**: 
- **Catastrophic forgetting**: 
- **Learning rate / batch size / epochs / gradient accumulation**: 

---

## Capítulo 8: Dataset Engineering

### Antes de leer

- [ ] ¿Qué creés que importa más para entrenar un modelo: muchos datos o datos muy buenos? ¿Por qué?
- [ ] ¿Usarías datos generados por una IA para entrenar otra IA? ¿Qué riesgos imaginás?
- [ ] Si tuvieras que armar un dataset de conversaciones de atención al cliente de un banco, ¿qué problemas de privacidad tendrías que resolver?

### A Data-Centric View of AI (recuadro de la introducción)

- [ ] [R] ¿Qué diferencia hay entre *model-centric AI* y *data-centric AI*? Dá un ejemplo de benchmark o competencia data-centric.

### 8.1 Data Curation

- [ ] [R] ¿Qué formato de datos necesitás para self-supervised finetuning, instruction finetuning, preference finetuning y para entrenar un reward model?
- [ ] [E] ¿Por qué es especialmente difícil conseguir datos de *chain-of-thought* y de *tool use*? ¿Por qué las anotaciones humanas pueden no ser ideales para agentes?
- [ ] [E] ¿Qué diferencia hay entre datos *single-turn* y *multi-turn*? ¿Qué enseña cada uno?
- [ ] [E] ¿Por qué el data curation también implica quitar datos? (Ejemplo del chatbot "arrogante" que reescribe sin que se lo pidan.)
- [ ] [R] ¿Cuáles son los tres criterios del data curation? Explicá la analogía con la cocina.

#### Data Quality

- [ ] [E] ¿Qué mostraron LIMA y el equipo de Yi sobre calidad vs. cantidad? ¿Qué desventaja tuvo LIMA?
- [ ] [R] ¿Cuáles son las seis características de los datos de alta calidad? Explicá cada una con un ejemplo.
- [ ] [E] ¿Por qué la autora usa "aligned with task requirements" en lugar de "correcto"?

#### Data Coverage

- [ ] [E] ¿Qué es la *data coverage* o diversidad? ¿Por qué las dimensiones de diversidad dependen de la aplicación? (Traductor francés–inglés vs. chatbot global.)
- [ ] [E] ¿Qué mostró "The Data Addition Dilemma"?
- [ ] [E] ¿Qué llama la atención de la mezcla de dominios de Llama 3 en pre-training y SFT (código y matemática) frente a preference finetuning? ¿Por qué?
- [ ] [E] ¿Cómo se decide la mezcla de datos correcta? ¿Qué mostró el experimento de Zhou et al. con tres datasets de 2.000 ejemplos?

#### Data Quantity

- [ ] [E] ¿Qué es la *ossification* y cuándo puede hacer que el finetuning sea peor que entrenar desde cero?
- [ ] [R] Además de calidad y diversidad, ¿qué tres factores influyen en cuántos datos necesitás?
- [ ] [E] ¿Por qué con pocos ejemplos conviene usar modelos más avanzados, mientras que con muchos ejemplos todos los modelos rinden parecido? ¿Qué regla práctica se deriva?
- [ ] [E] ¿Por qué conviene empezar con un dataset chico (por ejemplo, 50 ejemplos)? ¿Qué podés concluir si mejora y qué si no mejora?
- [ ] [R] ¿Cuáles son las tres formas de reducir la cantidad de datos de alta calidad necesarios entrenando primero con datos de menor calidad o menos relevantes?
- [ ] [E] ¿Cómo usás una curva de rendimiento vs. tamaño del dataset para estimar si vale la pena conseguir más datos?
- [ ] [E] ¿Qué mostró el paper de Chung et al. sobre la cantidad de tareas distintas en el finetuning?

#### Data Acquisition and Annotation

- [ ] [E] ¿Por qué los datos de tu propia aplicación suelen ser la mejor fuente? ¿Qué es un *data flywheel*?
- [ ] [E] Describí el proceso de ejemplo para armar un dataset (instrucción, respuesta) combinando fuentes. ¿Qué pasos "ocultos" suelen aparecer?
- [ ] [E] ¿Qué precauciones hay que tomar con los datasets públicos (licencias, origen)?
- [ ] [E] ¿Por qué crear la guía de anotación es una de las partes más difíciles? ¿Qué relación tiene con la guía de evaluación del capítulo 4?

### 8.2 Data Augmentation and Synthesis

- [ ] [R] ¿Qué diferencia hay entre *data augmentation* y *data synthesis*?

#### Why Data Synthesis

- [ ] [R] ¿Cuáles son las cinco razones para sintetizar datos?
- [ ] [E] ¿En qué casos los datos sintéticos pueden tener más calidad que los humanos? (Tool use, problemas de matemática complejos, datos de preferencia.)
- [ ] [E] ¿Por qué los datos sintéticos ayudan con la privacidad? Dá ejemplos de salud y seguros.

#### Traditional Data Synthesis Techniques

- [ ] [R] ¿Qué es la *procedural generation*? ¿Cuáles son los dos enfoques tradicionales de síntesis?
- [ ] [E] ¿Cómo se usan las plantillas para generar transacciones de tarjeta de crédito sintéticas? ¿Por qué los modelos de detección de fraude suelen arrancar así?
- [ ] [E] ¿Qué transformaciones simples se usan para aumentar imágenes y textos? ¿Cómo puede el reemplazo de palabras mitigar sesgos de género?
- [ ] [E] ¿Qué es la *perturbation*? ¿Qué mostró el "One Pixel Attack" y por qué entrenar con datos perturbados hace al modelo más robusto?
- [ ] [E] ¿Para qué sirve la simulación? ¿Qué es Sim2Real? ¿Por qué es valiosa para eventos raros, por ejemplo en finanzas?

#### AI-Powered Data Synthesis

- [ ] [E] ¿Cómo puede una IA simular APIs, humanos o adversarios? ¿Qué es *self-play*?
- [ ] [E] ¿Cómo se usan el parafraseo y la traducción para aumentar datos? ¿Qué es la *back-translation* y para qué sirve?
- [ ] [E] ¿Por qué se usan datos sintéticos mucho más en post-training que en pre-training?
- [ ] [E] ¿Cómo evitó NVIDIA el *first-position bias* al generar datos de preferencia con un AI judge?
- [ ] [E] ¿Cómo se generaron UltraChat y Alpaca?
- [ ] [E] ¿Qué es la *reverse instruction* y por qué produce datos de mejor calidad? ¿Cómo se usa para mejorar un modelo de forma iterativa?
- [ ] [E] ¿Cómo se pueden usar datos sintéticos para hacer finetuning de contexto largo?
- [ ] [R] Describí el pipeline de Llama 3 para generar datos de código (generación de problemas, soluciones, unit tests, corrección, traducción, back-translation).

#### Data verification

- [ ] [E] ¿Por qué la gente tiende a sintetizar datos que puede verificar? ¿Qué relación tiene con el evaluation-driven development?
- [ ] [E] ¿Qué formas de verificar datos sintéticos menciona el libro (functional correctness, AI verifiers, detectores de contenido de IA, detección de anomalías, heurísticas)?
- [ ] [R] ¿Qué heurísticas usaron los autores de Self-Instruct para filtrar ejemplos?

#### Limitations to AI-generated data

- [ ] [R] ¿Cuáles son las cuatro limitaciones principales de los datos generados por IA?
- [ ] [E] ¿Qué es la *superficial imitation*? ¿Por qué imitar las soluciones de un modelo maestro puede enseñarle a alucinar al alumno?
- [ ] [E] ¿Qué es el *model collapse*? ¿Por qué los eventos improbables quedan subrepresentados? ¿Cómo se puede evitar?
- [ ] [E] ¿Cómo pueden los datos sintéticos amplificar sesgos?
- [ ] [E] ¿Por qué los datos generados por IA oscurecen el *data lineage* y qué riesgos trae (copyright, contaminación de benchmarks)?

#### Model Distillation

- [ ] [R] ¿Qué es la *model distillation*? ¿Qué logró DistilBERT?
- [ ] [E] ¿Por qué no todos los modelos se pueden destilar legalmente?
- [ ] [E] ¿Por qué entrenar con datos sintéticos no siempre es distillation? (Caso Nemotron-4.) ¿Qué encontró el equipo de Llama 3 sobre entrenar con datos autogenerados sin verificar?

### 8.3 Data Processing

- [ ] [R] ¿Qué tips de eficiencia da el libro para procesar datos (orden de los pasos, trial runs, no modificar los datos originales)?

#### Inspect Data

- [ ] [E] ¿Qué estadísticas y distribuciones conviene mirar al inspeccionar un dataset? ¿Por qué hay que segmentarlas por fuente, tiempo y anotador?
- [ ] [E] ¿Por qué la inspección manual tiene "el mayor valor en relación con el prestigio" de cualquier actividad de ML?

#### Deduplicate Data

- [ ] [E] ¿Por qué los duplicados son un problema? Explicá el ejemplo de los lápices rojos y el estudio de Anthropic que repitió el 0,1% de los datos 100 veces.
- [ ] [R] ¿Qué tipos de duplicación existen en un dataset de documentos?
- [ ] [R] ¿Qué técnicas de deduplicación menciona el libro (comparación de a pares, hashing con MinHash o Bloom filter, reducción de dimensionalidad)?

#### Clean and Filter Data

- [ ] [E] ¿Qué conviene limpiar (formato, PII, datos no permitidos, baja calidad)? ¿Qué logró Databricks quitando tokens de HTML y Markdown?
- [ ] [E] ¿Qué heurística no obvia de baja calidad encontraron Kern et al.? ¿Qué técnicas sirven para filtrar si tenés más datos de los que podés usar (active learning, importance sampling)?

#### Format Data

- [ ] [E] ¿Por qué las instrucciones del finetuning pueden ser mucho más cortas que las del prompt engineering? Explicá el ejemplo de clasificación de alimentos.
- [ ] [E] ¿Por qué el prompt que usás con el modelo ajustado tiene que coincidir exactamente con el formato de entrenamiento? Dá ejemplos de errores.

### Escenarios integradores

- [ ] [A] Querés hacer finetuning de un modelo para clasificar reclamos de clientes de un banco en 12 categorías. Tenés 400 reclamos reales etiquetados, muy desbalanceados (casi no hay de "fraude"). Diseñá una estrategia que combine datos reales, augmentation y síntesis. ¿Cómo verificarías la calidad?
- [ ] [A] El área legal no permite usar datos reales de clientes para entrenar. ¿Cómo generarías un dataset sintético de conversaciones de atención al cliente sobre préstamos? ¿Qué riesgos de model collapse y de sesgo tendrías que cuidar?
- [ ] [A] Revisando tu dataset de entrenamiento descubrís que dos anotadores dan puntajes mucho más altos que el resto y que hay muchas respuestas duplicadas. Describí qué pasos de procesamiento aplicarías y en qué orden.
- [ ] [A] Tu fintech quiere entrenar un modelo chico y barato que imite a un modelo comercial grande para responder dudas de clientes. ¿Qué tenés que revisar antes (licencias, data lineage)? ¿Qué riesgo de imitación superficial existe?
- [ ] [A] Necesitás un modelo para detectar fraude en transferencias, pero los fraudes reales son el 0,1% de los casos. ¿Qué técnicas de este capítulo (plantillas, simulación, perturbación) usarías para cubrir mejor la clase rara?

### Práctica del capítulo

Armá un dataset de 300 ejemplos (instrucción, respuesta) para una tarea financiera (por ejemplo, explicar en lenguaje simple conceptos como "plazo fijo UVA", "CFT" o "tasa nominal anual"):

1. Escribí a mano 20 ejemplos semilla de alta calidad.
2. Usá un modelo para generar más instrucciones a partir de una lista de temas y de las semillas, y después generá las respuestas.
3. Verificá con un AI judge (rúbrica del capítulo 4) y con heurísticas (largo, duplicados, respuestas que repiten la pregunta).
4. Deduplicá con similitud semántica y mirá a mano al menos 30 ejemplos.
5. Graficá la distribución de largos y temas.

**Qué aprendés:** que generar datos es fácil, pero verificarlos y asegurar diversidad es donde está el trabajo real.

### Glosario para completar

- **Data-centric vs. model-centric AI**: 
- **Data quality / coverage / quantity**: 
- **Single-turn vs. multi-turn data**: 
- **Ossification**: 
- **Data flywheel**: 
- **Annotation guideline**: 
- **Data augmentation vs. data synthesis**: 
- **Procedural generation / simulation / Sim2Real**: 
- **Perturbation**: 
- **Self-play**: 
- **Back-translation**: 
- **Reverse instruction**: 
- **Model collapse**: 
- **Superficial imitation**: 
- **Model distillation (teacher/student)**: 
- **Deduplication (MinHash, Bloom filter)**: 

---

## Capítulo 9: Inference Optimization

### Antes de leer

- [ ] Si tu chatbot tarda 8 segundos en empezar a responder, ¿dónde creés que se va ese tiempo?
- [ ] ¿Qué diferencia creés que hay entre una CPU y una GPU para correr modelos de IA?
- [ ] ¿Qué harías para que un modelo cueste la mitad sin cambiar de proveedor?

### 9.1 Understanding Inference Optimization

- [ ] [R] ¿En qué tres niveles se puede optimizar la inferencia? ¿Por qué es un campo interdisciplinario?

#### Inference Overview

- [ ] [R] ¿Qué diferencia hay entre un *inference server* y un *inference service*?
- [ ] [R] ¿Qué significa que una tarea sea *compute-bound* y qué significa que sea *memory bandwidth-bound*? Dá un ejemplo de cada una.
- [ ] [E] ¿Qué ambigüedad tiene el término *memory-bound*? ¿Por qué la limitación de capacidad de memoria termina siendo un problema de ancho de banda?
- [ ] [R] ¿Qué es la *arithmetic intensity* y qué muestra un *roofline chart*?
- [ ] [E] ¿Por qué el *prefill* es compute-bound y el *decode* es memory bandwidth-bound? ¿Por qué se suelen separar en producción?
- [ ] [E] ¿Qué diferencia hay entre APIs *online* y *batch*? ¿Qué casos de uso son ideales para batch?
- [ ] [E] ¿Qué es el *streaming mode*? ¿Qué gana y qué riesgo tiene?
- [ ] [E] ¿En qué se diferencia la "batch inference" del ML tradicional de las batch APIs de foundation models?

#### Inference Performance Metrics

- [ ] [R] ¿Qué miden TTFT, TPOT, TBT e ITL? ¿Cuál es la fórmula de la latencia total?
- [ ] [E] ¿Qué TPOT alcanza para la mayoría de los casos en modo streaming y por qué?
- [ ] [E] ¿Por qué el TTFT que ve el usuario puede ser muy distinto del que ve el modelo en consultas con CoT o agentes? ¿Qué es *time to publish*?
- [ ] [E] ¿Por qué el promedio de latencia puede ser engañoso? ¿Qué percentiles conviene mirar?
- [ ] [R] ¿Qué es el *throughput* y en qué unidades se mide (TPS, RPS, RPM)?
- [ ] [E] Hacé la cuenta: si un sistema cuesta USD 2 por hora y genera 100 tokens/s, ¿cuánto cuesta un millón de tokens de salida?
- [ ] [E] ¿Qué trade-off hay entre latencia y throughput? ¿Qué es el *goodput* y por qué es mejor métrica que el throughput solo?
- [ ] [E] ¿Por qué la "GPU utilization" de `nvidia-smi` es engañosa? ¿Qué miden MFU y MBU?
- [ ] [E] Calculá el MBU de un modelo de 7B en FP16 que genera 100 tokens/s en una GPU con 2 TB/s de ancho de banda. ¿Qué te dice eso sobre la importancia de la cuantización?
- [ ] [E] ¿Por qué el MFU de entrenamiento suele ser más alto que el de inferencia? ¿Por qué tener alta utilización no es el objetivo final?

#### AI Accelerators

- [ ] [E] ¿Por qué AlexNet y las GPUs fueron clave para el boom del deep learning?
- [ ] [R] ¿Qué es un acelerador? ¿Cuál es la diferencia principal entre una CPU y una GPU?
- [ ] [E] ¿Por qué están surgiendo chips especializados en inferencia? ¿En qué se diferencian de los de entrenamiento?
- [ ] [R] ¿Cuáles son las tres características principales para evaluar un acelerador?
- [ ] [E] ¿Por qué la cantidad de FLOP/s depende de la precisión numérica?
- [ ] [R] Describí los tres niveles de memoria de una GPU (CPU DRAM, HBM, SRAM on-chip) con sus velocidades y tamaños aproximados.
- [ ] [E] ¿Por qué hay interés en lenguajes como CUDA, Triton y ROCm?
- [ ] [E] ¿Por qué el consumo eléctrico es un cuello de botella? ¿Qué es el TDP?
- [ ] [R] ¿Qué tres preguntas tenés que hacerte al elegir aceleradores?

### 9.2 Inference Optimization

- [ ] [E] Explicá la analogía del arquero para los niveles de optimización (modelo, hardware, servicio). ¿Por qué distintos proveedores pueden servir "el mismo modelo" con distinta calidad?

#### Model Optimization

- [ ] [R] ¿Cuáles son las tres características de los transformers autoregressive que hacen costosa la inferencia?
- [ ] [R] ¿Qué técnicas de *model compression* menciona el libro? ¿Qué dos significados tiene *pruning*?
- [ ] [E] ¿Por qué el pruning es menos común en la práctica que la cuantización de pesos?
- [ ] [E] ¿Por qué un token de salida es mucho más caro que uno de entrada, en costo y en latencia?
- [ ] [E] ¿Cómo funciona el *speculative decoding*? Explicá el rol del *draft model* y del *target model*.
- [ ] [E] ¿Cuáles son las tres ideas que hacen que el speculative decoding funcione sin aumentar la latencia? ¿De qué depende la *acceptance rate*?
- [ ] [E] ¿Qué es *inference with reference* y en qué casos sirve?
- [ ] [E] ¿Qué es el *parallel decoding*? ¿En qué se diferencian Lookahead decoding (Jacobi) y Medusa? ¿Por qué hace falta verificar los tokens?
- [ ] [R] ¿Qué es el *KV cache* y por qué solo se usa en inferencia?
- [ ] [E] ¿Cómo crece el KV cache con el largo de la secuencia y el batch size? Calculá el KV cache de Llama 2 13B con la fórmula del libro (batch 32, secuencia 2.048, 2 bytes).
- [ ] [R] ¿Cuáles son los tres grupos de técnicas para optimizar el attention mechanism?
- [ ] [E] Explicá *local windowed attention*, *multi-query attention*, *grouped-query attention* y *cross-layer attention*. ¿Por qué solo se pueden aplicar en entrenamiento o finetuning?
- [ ] [E] ¿Qué logró Character.AI con esas técnicas?
- [ ] [R] ¿Qué es PagedAttention (vLLM)? ¿Qué otras técnicas optimizan el KV cache?
- [ ] [R] ¿Qué es un *kernel*? ¿Qué hace FlashAttention?
- [ ] [R] Explicá las cuatro técnicas comunes en kernels: *vectorization*, *parallelization*, *loop tiling* y *operator fusion*.
- [ ] [R] ¿Qué es el *lowering* y qué hace un compilador de ML? Nombrá algunos.
- [ ] [E] ¿Qué pasos de optimización aplicó el equipo de PyTorch a Llama-7B?

#### Inference Service Optimization

- [ ] [E] ¿Por qué las técnicas a nivel servicio no deberían cambiar la calidad del modelo, a diferencia de muchas a nivel modelo?
- [ ] [E] Explicá *static batching*, *dynamic batching* y *continuous batching* con la analogía del colectivo. ¿Qué problema resuelve el continuous batching?
- [ ] [E] ¿Por qué separar prefill y decode en máquinas distintas mejora el rendimiento? ¿De qué depende la proporción de instancias de prefill y de decode?
- [ ] [E] ¿Qué es el *prompt caching*? ¿Cuándo es más útil? Hacé la cuenta del ejemplo: system prompt de 1.000 tokens y un millón de llamadas diarias.
- [ ] [R] ¿Qué es la *replica parallelism*? ¿Por qué ubicar modelos en GPUs es un problema de *bin-packing*?
- [ ] [E] ¿Qué es la *tensor parallelism* y qué dos beneficios tiene? ¿Qué es la *pipeline parallelism* y por qué se evita en aplicaciones sensibles a la latencia?
- [ ] [R] ¿Qué son la *context parallelism* y la *sequence parallelism*?
- [ ] [R] Según el resumen, ¿cuáles son las técnicas de mayor impacto en la mayoría de los casos?

### Escenarios integradores

- [ ] [A] Tu chatbot de home banking tiene un system prompt de 3.000 tokens con todas las políticas del banco, y las respuestas son cortas. Los usuarios se quejan de que tarda en empezar a responder. ¿Qué métrica mirarías y qué técnicas aplicarías primero?
- [ ] [A] Todas las noches tenés que analizar 500.000 transacciones del día para generar resúmenes de riesgo por cliente. ¿Qué tipo de API usarías y por qué? ¿Cuánto podrías ahorrar?
- [ ] [A] Tu servicio procesa 100 solicitudes por minuto, pero solo 40 cumplen el SLO de TTFT < 500 ms y TPOT < 80 ms. ¿Cuál es tu goodput? ¿Qué harías para mejorarlo?
- [ ] [A] Tu banco aloja un modelo de 70B en sus propios servidores para cumplir regulaciones. No entra en una sola GPU de 80 GB en FP16. ¿Qué opciones tenés (cuantización, tipos de paralelismo)? ¿Cuál elegirías si lo más importante es la latencia?
- [ ] [A] El p50 de TTFT de tu asistente de inversiones es 300 ms, pero el p99 es 9 segundos. ¿Qué hipótesis investigarías? ¿Por qué no alcanza con mirar el promedio?

### Práctica del capítulo

Medí el rendimiento de inferencia de un modelo, por API o local (por ejemplo, con Ollama o vLLM):

1. Escribí un pequeño cliente (en Java con Spring o en Python) que use streaming y mida TTFT, TPOT y latencia total para 50 consultas de distinto largo.
2. Calculá p50, p90 y p99, y graficá TTFT vs. largo del input.
3. Repetí con un system prompt largo, con y sin prompt caching (si tu proveedor lo soporta), y compará costo y TTFT.
4. Si corrés local: compará el mismo modelo en dos niveles de cuantización (por ejemplo, Q8 y Q4) y mirá velocidad y calidad.

**Qué aprendés:** a medir de verdad la latencia y el costo, y a ver con tus propios números el efecto de la cuantización y del caching.

### Glosario para completar

- **Inference server / inference service**: 
- **Compute-bound vs. memory bandwidth-bound**: 
- **Roofline chart / arithmetic intensity**: 
- **Online vs. batch API / streaming**: 
- **TTFT / TPOT / ITL**: 
- **Percentiles (p50, p90, p99)**: 
- **Throughput / goodput / SLO**: 
- **MFU / MBU**: 
- **Accelerator / GPU / TPU / HBM / SRAM**: 
- **Pruning**: 
- **Speculative decoding (draft / target model)**: 
- **Parallel decoding (Medusa, Lookahead)**: 
- **KV cache / PagedAttention**: 
- **Multi-query / grouped-query attention**: 
- **Kernel / FlashAttention / operator fusion**: 
- **Static / dynamic / continuous batching**: 
- **Prompt caching**: 
- **Replica / tensor / pipeline parallelism**: 

---

## Capítulo 10: AI Engineering Architecture and User Feedback

### Antes de leer

- [ ] Dibujá (en papel) cómo te imaginás la arquitectura de un chatbot bancario en producción: ¿qué componentes tiene además del modelo?
- [ ] ¿Cómo sabrías si los usuarios están conformes con tu asistente, si casi nadie toca el botón de "me gusta"?
- [ ] ¿Qué cosas cachearías y qué cosas nunca cachearías en una aplicación financiera?

### 10.1 AI Engineering Architecture

- [ ] [R] ¿Cuál es la arquitectura más simple de una aplicación de IA? ¿Cuáles son los cinco pasos con los que se va ampliando?

#### Step 1. Enhance Context

- [ ] [E] ¿Por qué la construcción de contexto es lo primero que se suele agregar? ¿En qué se diferencian los proveedores en su soporte para contexto y herramientas?

#### Step 2. Put in Guardrails

- [ ] [R] ¿Contra qué dos tipos de riesgo protegen los *input guardrails*?
- [ ] [E] ¿De qué formas puede filtrarse información privada hacia una API externa? ¿Qué tipos de datos sensibles se suelen detectar?
- [ ] [E] ¿Qué dos opciones tenés si una consulta contiene información sensible? Explicá el enmascarado con un *reverse PII map*.
- [ ] [R] ¿Cuáles son las dos funciones de los *output guardrails*? Nombrá fallas de calidad y fallas de seguridad típicas.
- [ ] [E] ¿Cómo ayuda la lógica de reintentos? ¿Qué costo tiene y cómo se reduce la latencia haciendo llamadas en paralelo?
- [ ] [E] ¿Cuándo conviene derivar a un humano? Dá ejemplos de criterios.
- [ ] [E] ¿Qué trade-offs tienen los guardrails (confiabilidad vs. latencia, problemas con streaming)? ¿Cómo cambia lo que necesitás si usás una API externa o alojás tu propio modelo?

#### Step 3. Add Model Router and Gateway

- [ ] [E] ¿Qué beneficios tiene un *router*? ¿Qué rol cumple el *intent classifier*?
- [ ] [E] ¿Cómo ayuda el intent classifier con consultas fuera de alcance y consultas ambiguas? (Ejemplo "Freezing".)
- [ ] [E] ¿Qué es un *next-action predictor*? ¿Por qué los routers deben ser rápidos y baratos?
- [ ] [E] ¿Qué hacés si una consulta crece más allá del context limit del modelo al que iba a ir?
- [ ] [R] ¿Cuál es el patrón de aplicación más común según el libro (routing, retrieval, generación, scoring)?
- [ ] [R] ¿Qué es un *model gateway*? ¿Qué funcionalidades ofrece (interfaz unificada, control de acceso, gestión de costos, fallback, load balancing, logging)?

#### Step 4. Reduce Latency with Caches

- [ ] [R] ¿Qué diferencia hay entre *exact caching* y *semantic caching*?
- [ ] [E] ¿Qué consultas conviene cachear y cuáles no? ¿Qué políticas de desalojo menciona el libro (LRU, LFU, FIFO)?
- [ ] [E] Explicá el ejemplo de fuga de datos por caché (la política de devoluciones que depende del tipo de membresía).
- [ ] [E] ¿Cómo funciona el semantic caching? ¿Por qué su valor es "más dudoso"? ¿Cuándo puede valer la pena?

#### Step 5. Add Agent Patterns

- [ ] [E] ¿Qué agregan los patrones agénticos (loops, write actions) a la arquitectura? ¿Qué riesgos traen?

#### Monitoring and Observability

- [ ] [R] ¿Qué miden MTTD, MTTR y CFR? ¿Qué significa no conocer tu CFR?
- [ ] [E] ¿Qué diferencia hay entre *monitoring* y *observability*?
- [ ] [E] ¿Por qué hay que diseñar las métricas a partir de los modos de falla que querés detectar? Dá ejemplos (alucinación, costos).
- [ ] [E] ¿Qué métricas conversacionales simples podés seguir (cortes de generación, turnos por conversación, tokens por input y output)?
- [ ] [E] ¿Por qué conviene medir la correlación de tus métricas con la *north star metric* del negocio?
- [ ] [E] ¿Por qué las métricas tienen que poder desglosarse por usuario, versión, prompt y tiempo?
- [ ] [E] ¿Qué diferencia hay entre métricas, logs y traces? Describí el proceso típico de debugging con los tres.
- [ ] [R] Según la regla general, ¿qué hay que loguear?
- [ ] [E] ¿Por qué igual conviene inspeccionar datos de producción a mano todos los días?
- [ ] [R] ¿Qué tres tipos de *drift* menciona el libro?

#### AI Pipeline Orchestration

- [ ] [R] ¿Cuáles son los dos pasos de un *orchestrator* (definición de componentes y chaining)?
- [ ] [E] ¿Por qué conviene empezar sin un orquestador? ¿Qué tres aspectos evaluarías al elegir uno?
- [ ] [E] ¿Cómo reducís la latencia al diseñar el pipeline? (Ejemplo de routing y remoción de PII en paralelo.)

### 10.2 User Feedback

- [ ] [E] ¿Por qué el feedback de usuarios es todavía más importante en aplicaciones de IA? ¿Qué relación tiene con el *data flywheel* y con la privacidad?

#### Extracting Conversational Feedback

- [ ] [R] ¿Qué diferencia hay entre *explicit feedback* e *implicit feedback*?
- [ ] [E] ¿Cómo revela preferencias la forma en que un usuario responde? (Ejemplo de los hoteles en Sídney.)
- [ ] [R] ¿Para qué tres cosas se usa el feedback extraído de conversaciones?
- [ ] [R] ¿Qué señales de *natural language feedback* menciona el libro (terminación temprana, corrección de errores, pedidos de confirmación, ediciones del usuario, quejas, sentimiento, tasa de rechazo del modelo)?
- [ ] [E] ¿Por qué una edición del usuario es una fuente valiosa de datos de preferencia?
- [ ] [E] ¿Qué otras señales vienen de acciones y no de mensajes (regeneración, organización de conversaciones, largo, diversidad del diálogo)? ¿Por qué su interpretación depende de la aplicación?
- [ ] [E] ¿Qué ventajas y desventajas tiene el feedback explícito frente al implícito?

#### Feedback Design

- [ ] [R] ¿En qué momentos del recorrido del usuario conviene pedir feedback?
- [ ] [E] ¿Por qué el usuario debería poder completar su tarea aunque el modelo se equivoque? Dá ejemplos de colaboración humano–IA (como el *inpainting*).
- [ ] [E] ¿Qué se puede hacer cuando el modelo tiene baja confianza? ¿Qué trade-off tiene mostrar dos respuestas completas o parciales?
- [ ] [E] ¿Hay que pedir feedback positivo? Presentá los argumentos de los dos lados.
- [ ] [E] ¿Por qué se cita a Midjourney y GitHub Copilot como buenos diseños de feedback? ¿Por qué es más difícil para apps independientes como ChatGPT?
- [ ] [E] ¿Por qué hace falta contexto junto con el feedback y qué implica para la privacidad (por ejemplo, el *data donation flow*)?
- [ ] [E] ¿Qué errores de diseño de feedback menciona la autora (pedir lo imposible, opciones confusas como el caso de Luma)? ¿Qué impacto tiene que el feedback sea público o privado?

#### Feedback Limitations

- [ ] [R] Explicá cuatro sesgos del feedback: *leniency bias*, *randomness*, *position bias* y *preference bias*.
- [ ] [E] ¿Cómo se puede reducir el leniency bias? (Ejemplo de Uber y las opciones reescritas.)
- [ ] [E] ¿Qué es un *degenerate feedback loop*? Explicá el ejemplo de los videos y el de las fotos de gatos.
- [ ] [E] ¿Por qué entrenar con feedback de usuarios puede volver al modelo complaciente (*sycophancy*)?

### Escenarios integradores

- [ ] [A] Diseñá la arquitectura completa de un asistente para clientes de una billetera virtual siguiendo los cinco pasos del capítulo. Para cada componente, explicá qué riesgo concreto resuelve en un contexto financiero.
- [ ] [A] Tu asistente usa una API externa y los usuarios a veces escriben su CBU, su DNI o el número de tarjeta en el chat. Diseñá los input guardrails y explicá cómo el modelo podría seguir respondiendo con esos datos enmascarados.
- [ ] [A] Querés cachear respuestas para bajar costos. ¿Cuáles de estas consultas cachearías y con qué tipo de caché: "¿Cuál es el horario de atención?", "¿Cuál es mi saldo?", "¿Qué comisión tiene una transferencia internacional?", "¿Por qué me rechazaron el préstamo?"? Justificá.
- [ ] [A] Desde hace dos semanas bajó el largo promedio de las respuestas de tu chatbot y subió la tasa de usuarios que reformulan su pregunta. No hiciste deploys. Usando lo de observability y drift, ¿qué investigarías y en qué orden?
- [ ] [A] Diseñá el sistema de feedback para un asistente que ayuda a analistas de crédito a redactar informes. ¿Qué señales explícitas e implícitas recolectarías? ¿Qué sesgos tendrías que vigilar?
- [ ] [A] Tu equipo propone reentrenar el modelo cada mes con los "me gusta" de los usuarios. ¿Qué riesgos de degenerate feedback loop y de sycophancy ves en un asesor de inversiones? ¿Qué propondrías?

### Práctica del capítulo

Integrá en un mini proyecto lo que construiste en capítulos anteriores (por ejemplo, el RAG del capítulo 6), siguiendo los pasos del capítulo. En Java, Spring Boot es una buena base:

1. Agregá un input guardrail que enmascare DNI, CBU y números de tarjeta antes de llamar al modelo y los desenmascare en la respuesta.
2. Agregá un router simple (intención: consulta de producto / fuera de alcance / derivar a humano).
3. Implementá un gateway mínimo que permita cambiar de proveedor de modelo por configuración y tenga un fallback.
4. Agregá un caché exacto para preguntas genéricas.
5. Logueá todo (prompt final, modelo, parámetros de sampling, tiempos de cada paso, tokens) con un ID de trace por request, y agregá un botón de feedback (pulgar arriba/abajo) que guarde el contexto.

**Qué aprendés:** a pensar la aplicación como un sistema completo, que es justamente donde un futuro arquitecto de software aporta más valor.

### Glosario para completar

- **Input / output guardrails**: 
- **PII masking / reverse PII map**: 
- **Router / intent classifier / next-action predictor**: 
- **Model gateway**: 
- **Exact vs. semantic caching**: 
- **Eviction policy (LRU, LFU, FIFO)**: 
- **MTTD / MTTR / CFR**: 
- **Monitoring vs. observability**: 
- **Metrics / logs / traces**: 
- **Drift**: 
- **Orchestrator / chaining**: 
- **Explicit vs. implicit feedback**: 
- **Natural language feedback**: 
- **Leniency / position / preference bias**: 
- **Degenerate feedback loop**: 
- **Sycophancy**: 

---

## Epilogue

- [ ] [E] Según la autora, ¿qué es lo más difícil de la escritura técnica? ¿Qué relación tiene con el método de estudio que estás usando con esta guía?
- [ ] [A] Ahora que terminaste el libro, elegí un problema real del sector financiero que te gustaría resolver con IA. Escribí en una página: el caso de uso, si lo construirías (capítulo 1), cómo lo evaluarías (capítulos 3–4), qué técnica de adaptación usarías primero (capítulos 5–7), qué datos necesitarías (capítulo 8), cómo controlarías costo y latencia (capítulo 9) y cuál sería su arquitectura (capítulo 10).

---

## Registro de repaso

| Capítulo | Fecha de lectura | Repaso a la semana | Repaso al mes | Preguntas que fallé |
|---|---|---|---|---|
| Preface | | | | |
| 1. Introduction to Building AI Applications with Foundation Models | | | | |
| 2. Understanding Foundation Models | | | | |
| 3. Evaluation Methodology | | | | |
| 4. Evaluate AI Systems | | | | |
| 5. Prompt Engineering | | | | |
| 6. RAG and Agents | | | | |
| 7. Finetuning | | | | |
| 8. Dataset Engineering | | | | |
| 9. Inference Optimization | | | | |
| 10. AI Engineering Architecture and User Feedback | | | | |
| Epilogue | | | | |