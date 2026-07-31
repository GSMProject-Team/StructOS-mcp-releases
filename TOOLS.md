# StructOS — MCP Tools Manifest

> Public interface of the StructOS MCP server. **Implementation is proprietary** (licensed product — see README). This manifest lists the tools the server exposes.

Total tools: **246**, grouped by domain.


## lira* (94)
- **lira_add_area_load**(plate_id, intensity_kpa, case, direction) — KK: Пластинаға площадная жүктеме жазбасын құру (РАСТАЛҒАН doc-6 type-16, dir 3 = төмен Z). RU: Запись
- **lira_add_bar_load**(element_ids, load_case_id, load_type, direction, value, value_end, position, coordinate_system, dry_run) — Линейная нагрузка на стержень (distributed/trapezoidal/point). dry_run=True — план.
- **lira_add_element**(ke_type, nodes, stiffness_id) — KK: Кез келген (соның ішінде сирек) КЭ типті элемент қосу. RU: Добавить элемент любого типа КЭ.
- **lira_add_element_by_nodes**(ke_type, node_ids, stiffness_id, dry_run) — KK: КЭ элементін түйіндерін тізіп қосу («Добавить элемент, перечислив узлы»). dry_run=True жоспар;
- **lira_add_nodal_load**(fz, fx, fy, load_case) — KK: Активті модельдің түйіндеріне сосредоточенная күш қосу + δ-мен тексеру — GUI pipeline арқылы
- **lira_add_node**(x, y, z) — KK: Координата бойынша түйін қосу. RU: Добавить узел по координатам. EN: Add a node at (x,y,z)
- **lira_add_plate_load**(element_ids, load_case_id, direction, value, dry_run) — Площадная нагрузка на плиту (кН/м²). dry_run=True — план. EN: Uniform SURFACE load on plate(s) —
- **lira_add_settlement**(node_ids, load_case_id, dz, dx, dy, dry_run) — KK: Тіреу орын ауысуы (settlement) — түйін(дер)ге мәжбүр орын ауысу dx/dy/dz (м). dry_run=True жоспар.
- **lira_add_stiffness**(name, section_spec, dry_run) — KK: Жаңа қима/жёсткость анықтау («Добавить жесткость»). dry_run=True жоспар. RU: Определить новую
- **lira_add_temperature_load**(element_ids, load_case_id, delta_t, dry_run) — KK: Температуралық жүктеме ΔT (°C) элемент(тер)ге. dry_run=True жоспар. Нақты жазу — COM форматы
- **lira_audit_coverage**() — Разбить 314 🔧-функций аудита по категориям + чем каждая закрыта (честно: панели/меню — GUI).
- **lira_build_geometry**(payload) — Построить геометрию LIRA из готового payload (узлы/элементы/сечения). Гейт записи.
- **lira_close**() — Закрыть открытый документ LIRA. Нужен STRUCTOS_LIRA_ENABLE_WRITE.
- **lira_close_test_models**() — KK: Барлық STRUCTOS-префиксті scratch құжаттарды САҚТАМАЙ жабу (нақты модельге тимейді). RU: Закрыть
- **lira_compute_envelope**(element_id) — Вычислить РСУ/РСН ОГИБАЮЩУЮ (governing N/Qy/Qz/Mx/My/Mz max/min) для одного стержня в
- **lira_copy_nodes**(node_ids, dx, dy, dz) — KK: Түйіндерді (dx,dy,dz)-пен жаңа түйін етіп көшіру. RU: Копировать узлы со смещением. EN: Copy
- **lira_create_block**(element_ids, block_type, name, dry_run) — KK: Элементтерді құрылымдық блокқа біріктіру («Создать блок»). dry_run=True жоспар; тірі жазу —
- **lira_create_model**(description, build) — Создать полную расчётную модель из описания на естественном языке (нагрузки СП РК + каркас КЭ10).
- **lira_create_rsu_combination**(name, load_cases, code, dry_run) — Создать сочетание РСУ с коэффициентами СП РК EN 1990. dry_run=True — формула без записи.
- **lira_create_test_model**(n_nodes, n_bars) — KK: Шағын СИНТЕТИКАЛЫҚ тест модель құру (STRUCTOS-префиксті, қауіпсіз песочница). RU: Создать
- **lira_delete_elements_via_gui**(window_substr, confirm) — KK: GUI арқылы таңдалған элементтерді жою — ТЕК синтетикалық тест модельде. ШАРТ: элемент алдын ала
- **lira_delete_test_model_demo**(n_nodes, n_bars) — KK: ТОЛЫҚ АВТОНОМДЫ delete демосы: синтетикалық модель құр→COM-мен бәрін таңда→GUI «Удаление
- **lira_full_results**(load_case) — KK: Шешілген модельдің ТОЛЫҚ нәтижесін бір шақыруда жинау — displacements + reactions + forces +
- **lira_generate_building**(text, dry_run) — KK: Мәтіннен ТОЛЫҚ ғимарат ЛИРА-да жасау — 'N қабатты болат каркас, LxW м, ...' брифінен тор-каркас
- **lira_generate_node_grid**(x0, y0, z0, nx, ny, dx, dy) — KK: XY жазықтығында nx×ny тұрақты түйін торын генерациялау (сетка). RU: Сгенерировать регулярную
- **lira_generate_report**(task_folder, config_path, output_path) — Сгенерировать Word-отчёт (.docx) по задаче ЛИРА-САПР. task_folder — папка задачи (подпапки
- **lira_get_elements**(elem_type) — Полная геометрия ПО ЭЛЕМЕНТАМ открытой модели LIRA — координаты концевых узлов,
- **lira_get_results**(doc_name, category, load_case) — Прочитать результаты: перемещения, реакции, стальные проверки КНС/1ПС/2ПС (через CSV-таблицы).
- **lira_gui_add_bar_load**(element_ids, load_case_id, direction, value, dry_run) — Добавить линейную нагрузку на стержень через GUI ЛИРА (без курсора). dry_run=True — план.
- **lira_gui_add_settlement**(node_ids, load_case_id, dz, dry_run) — Осадка опоры через GUI ЛИРА. dry_run=True — план. EN: Add a support settlement via LIRA's GUI,
- **lira_gui_add_temperature**(element_ids, load_case_id, delta_t, dry_run) — Температурная нагрузка через GUI ЛИРА. dry_run=True — план. EN: Add a temperature load via LIRA's
- **lira_gui_export_excel**(table_type, output_path, dry_run) — Экспорт таблиц результатов через «Книга отчётов». dry_run=True — план. EN: Export result tables via
- **lira_gui_send_command**(command_id, dry_run) — KK: ЛИРА фреймге WM_COMMAND (белгілі командалық id) жіберу (курсорсыз PostMessage). НАЗАР: ribbon
- **lira_gui_show_mosaic**(result_type, load_case) — KK: Нәтиже эпюрасын/мозаикасын ЛИРА GUI-де көрсету (курсорсыз ribbon UIA-invoke) — тек КӨРІНІС
- **lira_ifc_import**(path, build) — Импорт IFC через IfcOpenShell в payload LIRA (build=True — построить в LIRA).
- **lira_joint_forces**(element_ids, position, load_cases, profile, section_id) — Расчётное усилие для ГРУППЫ одинаковых узлов = взять по группе МАКСИМУМ КАЖДОГО загружения и
- **lira_km_read**(output_path, include_forces, load_cases) — Прочитать все КМ-данные из открытой модели LIRA и записать lira_km_data.json (стержни, пластины,
- **lira_list_ke_library**() — Список всех типов КЭ (🔧) — все создаются через lira_add_element. EN: List all КЭ finite-element types
- **lira_marked_to_tekla**(model_substr, build, save) — KK: LIRA-да БЕЛГІЛЕНГЕН стерженьдерді Tekla-ға көшіру — бір шақыруда (оқу→біріктіру→салу). model_substr
- **lira_natural_language**(text, dry_run) — Построить модель LIRA из текста (KK/RU/EN) — БЕЗ LLM, ОФФЛАЙН (regex). dry_run=True (по умолч.)
- **lira_open**(path) — Открыть документ LIRA через CoCreateInstance (НЕ GetActiveObject).
- **lira_profile_envelope**(section_id, profile) — Огибающая ULS-усилий по ВСЕМ элементам одного профиля (сечения) — типовое соединение ставится
- **lira_rationalize_reinforcement**(bands, elements, element_ids, total_area_m2, fon_diameter_mm, fon_spacing_mm, dop_spacing_mm) — Рационализация армирования плиты: сырое As из LIRA → практичная схема КЖ (фон ∅12@200 на всю
- **lira_read_arm_results**(element_type, thickness_mm, load_case, limit, concrete_class, rebar_class, fallback) — Прочитать результаты армирования из ЛИР-АРМ — на каждый КЭ ⌀, шаг, As (см²/м для плит,
- **lira_read_bar_forces**(element_ids, load_cases, combinations, envelope) — Прочитать ВНУТРЕННИЕ УСИЛИЯ стержней — N, Qy, Qz, Mx, My, Mz (кН, кН·м) по загружениям и сечениям.
- **lira_read_buckling**() — KK: Тұрақтылық (устойчивость) нәтижесі — LiraResultsAccess-те COM сұрауы ЖОҚ (🖱️), AUTORES кестесі/
- **lira_read_catalog**(query) — Каталог сечений и материалов (стальной сортамент + база знаний LIRA).
- **lira_read_construction_axes**() — KK: Модельдің құрылымдық осьтерін (тор сызықтары) оқу. RU: Прочитать конструктивные оси.
- **lira_read_construction_blocks**() — KK: Модельдің құрылымдық блоктарын оқу (элементтер/тип/қабат/марка/түс). RU: Прочитать
- **lira_read_displacements**(load_case) — KK: Шешілген модельдің БАРЛЫҚ узел бойынша орын ауыстыруын оқу — Ux,Uy,Uz (мм) + Фx,Фy,Фz (рад),
- **lira_read_element_rotation**(element_id) — Прочитать ориентацию профиля (rotation) стержня ЛИРА — локальные оси X/Y/Z, угол (град),
- **lira_read_frequencies**() — KK: Жеке тербеліс жиіліктерін оқу → [{mode, freq_hz, period_s}]. RU: Прочитать собственные частоты.
- **lira_read_handbook**(query, section) — Читает справку ЛИРА-САПР 2024 и ищет информацию по запросу.
- **lira_read_marked_bars**() — KK: LIRA-да ОТМЕЧЕННЫЕ (белгіленген) стержень КЭ-ін оқу — Tekla-ға дайын {elem,n1,n2,c1,c2,section,
- **lira_read_mode_shapes**(mode) — KK: Модальды пішінді (mode) түйін бойынша оқу. RU: Прочитать форму колебаний (mode) по узлам.
- **lira_read_model**() — Прочитать открытую модель LIRA — узлы, элементы, сечения, материалы (структурная сводка).
- **lira_read_model_table**(table_name) — Прочитать 🔧 входную таблицу открытой модели (через AllTables, read-only).
- **lira_read_mounting_stages**() — KK: Монтаждау кезеңдерін оқу (кезең + атауы + элементтер). RU: Прочитать стадии монтажа.
- **lira_read_plate_forces**(load_case) — KK: Пластина (КЭ42/44) усилиялары — Mx,My,Mxy (иілу), Nx,Ny (мембрана), Qx,Qy (қима) әр КЭ бойынша
- **lira_read_reactions**(load_case) — KK: Тірек реакцияларын оқу — LiraResultsAccess FragmLoads (Rx/Ry/Rz + Mx/My/Mz; расчётный фрагмент
- **lira_read_reinforcement**(element_ids, parsed) — Прочитать армирование (ЛИР-АРМ). parsed=True → распарсенные {element_id, as_req, utilization};
- **lira_read_rsu**() — Прочитать РСУ/РСН открытой модели по COM — формула сочетаний (каждое загружение × γf × ψ,
- **lira_read_rsu_combinations**() — KK: Ашық модельдің РСУ/РСН комбинацияларын оқу (анықтама + γf/ψ + формула). RU: Прочитать РСУ/РСН
- **lira_read_section_check**(element_ids) — Прочитать результаты подбора сечений (ЛИР-СТК). EN: Read the steel section-check results (ЛИР-СТК)
- **lira_read_sections**() — Прочитать ПОЛНУЮ таблицу сечений/жёсткостей — по каждой: id, имя, тип, материал (бетон/сталь по
- **lira_read_seismic_forces**() — KK: Сейсмикалық жүктеме күштерін оқу (элемент бойынша). RU: Прочитать сейсмические усилия.
- **lira_read_soil_model_params**() — KK: Грунт-модель параметр таблиц (C1/C2/E/Hc/осадка) + белсенді bed оқу. RU: Прочитать параметры
- **lira_read_soil_reactions**() — KK: Іргетас негізінің тағайындалған C1/C2 (bed) коэффициенттерін оқу. RU: Прочитать назначенные
- **lira_read_steel_check**() — Прочитать таблицу стальных проверок (ЛИР-СТК, kLiraCsvTable_Steel_src=111) — СЫРЫЕ строки.
- **lira_read_vibration_modes**(load_case) — KK: Табиғи тербеліс формалары — жиілік (Гц), период (с), модаль масса %, қатысу коэф. (динамикалық/
- **lira_reinforcement_to_kj**(rows, element_ids, width_mm, cover_mm, min_d, max_d, min_n) — Спецификация арматуры КЖ (ГОСТ 5781/СП РК): As → ⌀+кол-во/шаг. `rows` или чтение из LIRA.
- **lira_rotate_nodes**(node_ids, angle_deg, cx, cy) — KK: Түйіндерді Z осі (cx,cy) айналасында angle_deg-ке бұру. RU: Поворот узлов вокруг оси Z через
- **lira_run_analysis**(payload, analysis_type) — Запустить расчёт. С payload — цепочка собственного веса через текст-импорт; иначе активная модель.
- **lira_run_section_selection**(dry_run) — KK: Автоматты секция таңдауды (подбор сечений) іске қосу. dry_run=True жоспар. RU: Запустить
- **lira_run_staged_analysis**(dry_run) — KK: Кезеңдеп (монтаж) есептеу. dry_run=True жоспар. RU: Запустить расчёт по стадиям монтажа.
- **lira_save**(path) — Сохранить открытый документ LIRA (если задан path — SaveAs). Нужен STRUCTOS_LIRA_ENABLE_WRITE.
- **lira_select_all**(subj) — KK: Активті модельде БАРЛЫҚ объектіні COM арқылы таңдау (doc.Select("all",subj)) — жұмыс істейтін
- **lira_set_element_material**(elem, mat1, mat2, dry_run) — Назначить материал элементу. dry_run=True — план. EN: Assign material id(s) to an element
- **lira_set_foundation_mat**(element_ids, C1, C2, soil_type, target, dry_run) — Назначить винклеровское основание (C1,C2) элементам фундамента. soil_type → авто C1/C2 по
- **lira_set_hinges**(hinges) — Назначить шарниры (освобождения) на концах стержней. Гейт записи.
- **lira_set_model_table**(table_name, assignments) — ОБНОВИТЬ строки таблицы-назначения по id (UPSERT-безопасно, чисто откатывается).
- **lira_set_mounting_stage**(stage_id, element_ids, action, dry_run) — Добавить/убрать элементы в стадию монтажа. dry_run=True — план. EN: Assign/unassign elements to a
- **lira_set_mounting_stages**(stages) — Записать монтажные стадии (kLiraTable=23). stages = список названий стадий. Гейт записи.
- **lira_set_nodal_load_via_gui**(window_substr, fz, fx, fy, load_case, apply) — KK: GUI арқылы түйінге сосредоточенная сила қою — LIVE-картаға түскен «Задание нагрузок» pipeline.
- **lira_set_restraints**(restraints) — Назначить связи узлам. {узел: "XYZ"|["X","Y","UY"]}. Сливается с таблицей «Связи». Гейт записи.
- **lira_solve_with_loads**(payload, area_loads, element_loads, add_self_weight) — Построить+решить модель с площадными нагрузками. EN: Build a model WITH loads (area loads on plates
- **lira_tekla_sync_rotation**(lira_id, tekla_guid, dry_run) — Перенести угол ориентации профиля из стержня ЛИРА в балку Tekla. Читает угол из ЛИРА →
- **lira_to_idea_pipeline**(node_ids, lira_doc, load_cases, geometry_source) — Полный конвейер LIRA→IDEA — усилия → узлы → проверка CBFEM (Unity Check) каждого узла.
- **lira_to_rebar_design**(elements, concrete, steel, element_ids, cover_mm) — KK: LIRA M/Q/N → СП РК 5.03 бойынша As есептеу (иілу + ығысу) → {element_id, As_bot, As_top,
- **lira_to_tekla**(bars, build_json_path, build, model_substr) — Экспорт стальных элементов LIRA в Tekla (склейка КЭ в члены + build JSON; build=True — вставка в Tekla).
- **lira_translate_nodes**(node_ids, dx, dy, dz) — KK: Түйіндерді (dx,dy,dz)-ке жылжыту (перенос). RU: Перенос узлов на (dx,dy,dz). EN: Translate
- **lira_unselect_all**(subj) — KK: Таңдауды COM арқылы тазалау (doc.Unselect("all",subj)). RU: Снять выделение через COM.
- **lira_verify_beam**(spans, EI_kNm2, loads, lira_moment_kNm) — KK: Үздіксіз балканы buddyd16 (BSD) үш-момент/slope-deflection алгоритмімен есептеп,
- **lira_verify_reinforcement**(As_lira_mm2, b_mm, d_mm, Med_kNm, fck_MPa, fyk_MPa) — Проверка арматуры ЛИРА независимым расчётом (подход concrete-properties, MIT): требуемая

## tekla* (33)
- **tekla_add_dimensions**(drawing_id, dimension_type, dry_run) — Добавить размеры в существующий чертёж (drawing_id = марка чертежа, напр. '[1]'). Только Open API.
- **tekla_add_marks**(drawing_id, mark_content, dry_run) — Добавить маркировку деталей в чертёж (профиль/материал/длина/марка). Только Open API.
- **tekla_assembly_drawing**(output_folder, dry_run, export_formats) — Авто-генерация чертежей КМД для всех стальных сборок (логика x_drawer) — главная деталь,
- **tekla_build_connection_ideacon**(spec, out_path) — Собрать .ideaCon из spec узла (обход Checkbot). EN: Build a valid IDEA .ideaCon from a joint spec
- **tekla_capture_window**(title_substr, out_png, process_name) — Снять окно Tekla по заголовку. EN: PrintWindow-capture the Tekla window whose title contains
- **tekla_create_assembly_drawing**(assembly_guid, drawing_name, attributes, dry_run) — Создать сборочный чертёж (AssemblyDrawing) — по одному GUID или для всех сборок. Только Open API.
- **tekla_create_beam**(p1, p2, profile, material, name) — Создать стальную БАЛКУ в Tekla (p1→p2, мм). Нужен опт-ин записи Tekla.
- **tekla_create_column**(p1, p2, profile, material, name) — Создать стальную КОЛОННУ в Tekla (p1→p2, мм). Нужен опт-ин записи Tekla.
- **tekla_create_connection**(kind) — Создать болтовое/сварное соединение — НЕ РЕАЛИЗОВАНО.
- **tekla_create_ga_drawing**(view_name, scale, attributes, dry_run) — Создать чертёж общего расположения (КМ) — GADrawing. Только Open API, без курсора.
- **tekla_create_km_set**(output_folder, format, dry_run) — Полный конвейер комплекта КМ — все сборки→чертежи→размеры+марки→экспорт в PDF. Только Open API.
- **tekla_create_plate**(contour, thickness, material, name) — Создать ContourPlate в Tekla — контур (мм) + толщина (мм) через lira_to_tekla_mod.build_single_plate
- **tekla_export_ifc**(file_path) — Экспорт модели Tekla в IFC4. ВНИМАНИЕ: в Tekla 2021 нет IFC-экспорта в public Open
- **tekla_export_nc**(nc_settings) — Экспорт NC1/DSTV из активной модели Tekla (для ЧПУ) через helper. nc_settings —
- **tekla_firm_catalog**() — KK: Фирма Tekla шаблон кітапханасының толық каталогы — түр (кеңейтім) бойынша тізім + PURPOSE
- **tekla_firm_template**(purpose) — Найти готовый шаблон фирмы по назначению. EN: Resolve the firm's Tekla drawing template by
- **tekla_generate_building**(text, dry_run) — KK: Мәтіннен ТОЛЫҚ ғимарат Tekla-да жасау — бағана/балка create жоспарын құрады (офлайн). dry_run=True
- **tekla_get_drawings**() — KK: Ашық модельдегі сызбаларды тізу (DrawingHandler.GetDrawings) helper арқылы —
- **tekla_get_reports**(template, output_file) — Сгенерировать отчёт Tekla по всем объектам через helper. template — имя шаблона;
- **tekla_install_firm_templates**(dest_attributes_dir, overwrite) — Скопировать шаблоны фирмы в папку attributes модели Tekla. EN: Install the firm's template set
- **tekla_km_import**(json_path, dry_run, default_material) — Импортировать lira_km_data.json в Tekla — стержни→Beam, пластины→ContourPlate с ТОЧНЫМИ
- **tekla_km_sapr**(json_path, output_folder, scale, dry_run) — Сгенерировать полный комплект КМ — монтажная схема (GA), ведомость элементов, спецификация
- **tekla_lira_import**(build_json_path, model_substr, save) — Импорт из build-JSON LIRA КМ в Tekla (проверенный в продакшене путь через PowerShell).
- **tekla_natural_language**(text, dry_run) — Создать стальные элементы в Tekla из текста (KK/RU/EN) — БЕЗ LLM, ОФФЛАЙН (regex). Профиль → имя каталога
- **tekla_print_drawings**(drawing_ids, format, output_folder, dry_run) — Экспорт чертежей в PDF (drawing_ids=None — все). Только Open API.
- **tekla_pytekla_read**(types, scan_cap) — Прочитать открытую модель Tekla через PyTekla (Open API/pythonnet) — балки/колонны (профиль,
- **tekla_read**(object_types, names) — Прочитать все объекты модели Tekla (балки/колонны/плиты/болты/сварка/сборки).
- **tekla_read_joint_members**(node_mm, tol_mm, profile_contains) — Прочитать члены у узла из Tekla. EN: Read the frame members meeting near a node (mm) from the
- **tekla_run_numbering**() — Запустить нумерацию через helper. ВНИМАНИЕ: в Tekla 2021 нет runner нумерации —
- **tekla_stair_connect_truss**(secondary_end_a, secondary_end_b, near_xy, secondary_profile_like, primary_profile_like, component, config, model) — KK: Баспалдақ косоурының ұшын өзі ПЕРПЕНДИКУЛЯР қиылысатын ферма мүшесіне компонент-27 (торцевая
- **tekla_stair_sphere_finial**(x, y, z_base, name, material, cls, model) — KK: Тұтқа/стойка ұшына декоративті сфера-финиал жасау (3 диск: D38/D56/D38). RU: Создать
- **tekla_stair_trim_railing**(cut_xy, removed_top_xy, dry_run, threshold_mm, model) — Удалить элементы ограждения за обрезанным косоуром (только имена ограждения). EN: Trim railing
- **tekla_stair_verify_model**(model) — KK: Пинделген Tekla құбыры ШЫНЫМЕН қай модельге қосылғанын қайтару — жазбас бұрын дұрыс модель

## revit* (24)
- **revit_create_kj_sheet**(title, level, view_type, dry_run) — Создать лист КЖ (ViewSheet + штамп) в Revit. Запись — флаг STRUCTOS_REVIT_ENABLE_WRITE.
- **revit_document_info**() — Полная информация об открытой модели Revit — данные проекта, worksharing, активный вид, счётчики.
- **revit_element_count**() — Количество элементов по категориям + общее.
- **revit_export_ifc**() — Экспорт IFC из Revit (асинхронная очередь+poll, pyRevit Routes).
- **revit_get_categories**() — Категории модели (имя + id).
- **revit_get_element**(element_id) — Полные данные одного элемента + все его параметры (по ElementId).
- **revit_get_elements**(category) — Элементы одной категории (id/имя/тип) — beams/columns/walls/floors/foundations/trusses/
- **revit_get_families**() — Загружаемые семейства (id, имя, категория).
- **revit_get_family_types**(family_id) — Типы одного семейства (по ElementId семейства).
- **revit_get_linked_files**() — Связанные модели Revit (имя + статус загрузки).
- **revit_get_phases**() — Проектные фазы модели (по порядку).
- **revit_get_rebar_schedule**() — Экспорт ведомости арматуры в JSON — поз./диаметр/длина/кол-во/вес.
- **revit_get_rooms**() — Размещённые помещения (номер, имя, уровень, площадь м²).
- **revit_get_schedule_data**(schedule_id) — Содержимое одной спецификации (по ElementId) — текст строк/столбцов.
- **revit_get_schedules**() — Список спецификаций модели (id + имя) — передайте id в revit_get_schedule_data.
- **revit_get_sheets**() — Листы чертежей (номер, имя, id).
- **revit_get_views**() — Виды модели (не шаблоны) — имя, тип, id.
- **revit_get_warnings**() — Предупреждения модели (описание + id проблемных элементов).
- **revit_get_worksets**() — Пользовательские рабочие наборы (только в workshared-модели).
- **revit_place_rebar**(element_id, lira_results, diameter_mm, spacing_mm, cover_mm, dry_run) — Разместить арматуру в элемент(ах) Revit — из результатов LIRA (As→диаметр/шаг по СП РК) или
- **revit_project_units**() — Единицы измерения проекта (длина/площадь/объём/угол).
- **revit_read_model**() — Прочитать открытую модель Revit (элементы, уровни, оси, материалы) — pyRevit Routes 48884.
- **revit_search_elements**(query, limit) — Поиск элементов по имени/типу (без учёта регистра, подстрока).
- **revit_sync**() — Синхронизация с центральной моделью — НЕ РЕАЛИЗОВАНО.

## virtual* (19)
- **virtual_cancel_dialog**(window_title) — KK: Диалогты қауіпсіз ЖАБУ (IDCANCEL — бәрін тастайды, ЕШНӘРСЕ қолданбайды). Аты жоқ Cancel-і бар
- **virtual_click**(hwnd, x, y, button, double) — KK: НАҚТЫ тінтуірді ҚОЗҒАМАЙ (hwnd,x,y) клиент координатына клик (PostMessage). RU: Клик по
- **virtual_click_control**(window_title, control_text) — KK: Классик диалог батырмасын (OK/Отмена/Применить…) мәтіні бойынша Win32 BM_CLICK-пен басу
- **virtual_click_id**(window_title, ctrl_id) — KK: Контролды ctrl-id бойынша басу (BM_CLICK, курсорсыз). RU: Нажать контрол по ctrl-id. EN: Click any
- **virtual_dismiss_modals**() — KK: Кептеліп қалған МОДАЛЬ #32770 диалогтарды жабу (LIRA «VISOR … книга отчетов … ошибка» — жаңа
- **virtual_find_and_click**(window_title, control_name, control_type) — KK: UIA арқылы элементті атымен тауып invoke ету (координатсыз, ЕҢ СЕНІМДІ — модальді диалогтарда
- **virtual_find_element**(window_title, max_elements) — Список UIA-элементов окна (для отладки/поиска control_name). EN: List the UI-Automation controls
- **virtual_find_window**(title) — KK: Атауы `title`-ды қамтитын терезені табу (HWND). RU: Найти окно по части заголовка. EN: Find
- **virtual_invoke_control**(window_title, control_name, control_type) — KK: Контролды атымен ТЕРЕҢ UIA-walk арқылы тауып InvokePattern-мен басу — LIRA лентасында
- **virtual_mark_all_canvas**(window_substr, kind) — KK: LIRA model-view canvas-іне толық rubber-band жіберіп БАРЛЫҚ түйін/элементті «отметить» ету —
- **virtual_post_click**(window_title, ctrl_id) — KK: Ctrl-id бойынша БҰҒАТТАМАЙ басу (PostMessage BM_CLICK) — модаль диалог ашатын батырма үшін
- **virtual_press_default**(window_title) — KK: Диалогтың ӘДЕПКІ батырмасын (Применить/ОК) іске қосу (DM_GETDEFID/VK_RETURN, курсорсыз) — аты жоқ
- **virtual_read_ctrl**(window_title, ctrl_id) — KK: Контролдың мәтінін/күйін ctrl-id бойынша оқу (WM_GETTEXT, READ-ONLY). RU: Прочитать текст/состояние
- **virtual_set_check**(window_title, ctrl_id, checked) — KK: Диалог чекбоксын ctrl-id бойынша белгілеу/алу (BM_SETCHECK+BM_CLICK, курсорсыз). RU: Отметить
- **virtual_set_edit**(window_title, ctrl_id, text) — KK: Диалог Edit өрісіне ctrl-id бойынша мәтін жазу (WM_SETTEXT, курсорсыз). RU: Записать текст в Edit
- **virtual_set_window_text**(window_title, ctrl_id, text) — KK: Ctrl-id бойынша мәтінді win32 SetWindowText-пен орнату — LIRA custom edit-терінде WM_SETTEXT
- **virtual_type**(hwnd, text, mode) — Ввести текст без перемещения курсора. EN: Type `text` into window/control `hwnd` WITHOUT moving
- **virtual_type_number**(window_title, ctrl_id, text) — KK: LIRA custom сан-edit-іне НАҚТЫ таңба енгізу (SetFocus+EM_SETSEL+WM_CHAR) — мәнді COMMIT ететін
- **virtual_window_controls**(window_title) — KK: Классик диалогтың (#32770) бала-контролдарын Win32 арқылы тізу (UIA бос қайтарғанда — мыс.

## kzh* (11)
- **kzh_auto_details_from_dwg**(source, out_path) — АВТО «Ведомость деталей» ИЗ ГЕОМЕТРИИ чертежа: сам находит гнутые стержни (авто-слои), форма+
- **kzh_details_template**(details, out_path) — Параметрический шаблон «Ведомость деталей»: эскизы гнутых стержней (форма фиксирована, меняются
- **kzh_generate_beam**(beam_data) — Строит КЖ-чертёж балки (DXF) из данных LIRA. EN: Build a beam КЖ reinforcement drawing (DXF)
- **kzh_generate_column**(column_data) — KK: LIRA деректерінен колонна КЖ сызбасын (DXF) жасайды. column_data: {mark, width, depth,
- **kzh_generate_from_lira**(element_id, element_type, output_dir) — KK: LIRA элемент ID бойынша КЖ сызбасын автоматты жасайды — ашық ЕСЕПТЕЛГЕН модельден геометрия
- **kzh_generate_slab**(slab_data) — KK: LIRA деректерінен плита КЖ сызбасын (DXF) жасайды. slab_data: {mark, thickness, span_x,
- **kzh_plate_mosaic_scheme**(mosaic_png, thickness_mm, direction, cover_mm, spacing_mm) — Из СНИМКА мозаики ЛИРА (PNG) → КЖ-схема плиты + данные Ведомости деталей. Доп-зоны берутся ПО
- **kzh_rebar_schedule**(element_type, data) — Спецификация арматуры (ведомость расхода стали) элемента КЖ. EN: Rebar bending schedule / bill
- **kzh_spec_batch**(folder, pattern, recursive, export_path) — ПАКЕТ: все чертежи в папке → спецификации + СВОДНАЯ ведомость расхода стали. export_path(.xlsx)
- **kzh_spec_from_dwg**(path, export_path) — АВТО-спецификация арматуры ИЗ ЧЕРТЕЖА (.dwg/.dxf). Режим авто: структурные спец-блоки
- **kzh_spec_into_drawing**(source, out_path, x, y, scale, columns) — Прочитать чертёж → спецификация → ВСТАВИТЬ таблицу + ведомость В САМ ЧЕРТЁЖ и сохранить out_path.

## kj* (10)
- **kj_bvbs_export**(bars, project_name, steel_grade, output_file, profile, dry_run) — KK: Арматура позицияларын нағыз BVBS 2.0 (BF2D+checksum) .abs форматына (Германия, иілу
- **kj_clash_check**(elements, min_clearance) — KK: Арматура CLASH (қиылысу) тексеру — стерженьдер өзара + cover (СП РК min_clearance, мм).
- **kj_cutting_plan**(bars, stock_lengths) — KK: КЕСУ жоспары — зауыт ұзындықтарынан (stock 6/9/11.7/12м) минимум қалдық (greedy). bars:
- **kj_draw_autocad**(elements, output_file, dry_run) — KK: Арматура нәтижелерінен ҚАБАТТЫ AutoCAD DXF сызба (KJ-ARMAT-BOT/TOP, KJ-STIRRUP, KJ-DIM,
- **kj_full_auto**(lira_model_path, project_name, output_folder) — KK: ПОЛНЫЙ авто-КЖ из ОТКРЫТОЙ LIRA модели: читает ЖБ стержни → группирует по сечениям (=марки) →
- **kj_full_package**(project_name, elements, output_dir, dry_run) — KK: PKPM/YJK стилінде ONE-CLICK КЖ пакет — есеп→оптимизация→clash→сызба→ведомость(Excel)→BVBS→
- **kj_generate**(element_type, element_data, project_name) — KK: КЖ чертёж (DXF) элемента с ГОСТ штампом 21.101 + спецификацией. element_type: kolonna|balka|
- **kj_optimize**(elements) — KK: Арматура шығынын ОҢТАЙЛАНДЫРУ (Корея алгоритмі) — норманы сақтай отырып минимум салмақ
- **kj_rebar_design**(element_type, forces, geometry, concrete_class, rebar_class) — KK: LIRA/SAP күштерінен арматура есебі (СП РК 5.03-102). element_type: beam|slab|column|footing;
- **kj_weight_calc**(elements, output_excel, dry_run) — KK: Арматура ВЕДОМОСІ + салмақ (BBS): позиция/⌀/ұзындық/сан/масса + диаметр бойынша жиынтық +

## idea* (10)
- **idea_calculate**(connection_id) — KK: Узелге CBFEM есептеуін жүргізу. RU: Выполнить расчёт CBFEM узла.
- **idea_close_project**() — KK: Ашық жобаны жабу (сервис ашық қалады). RU: Закрыть открытый проект. EN: Close the active project.
- **idea_get_connections**() — KK: Жобадағы барлық узелдерді (қосылыстарды) тізімдеу. RU: Список всех узлов проекта.
- **idea_get_node_results**(node_id) — KK: Нақты узелдің IDEA нәтижесін қайтару (соңғы pipeline-дан). RU: Результат узла из последнего прогона.
- **idea_get_results**(connection_id) — KK: Unity Check нәтижелерін қайтару (плиталар/болттар/дәнекер). RU: Вернуть результаты Unity Check.
- **idea_open_project**(file_path) — KK: .ideaCon жобасын ашу. RU: Открыть проект .ideaCon. EN: Open a .ideaCon project file. Returns {ok, project_
- **idea_set_loads**(connection_id, loads) — KK: Узелге күштерді енгізу (LIRA/SAP-тан N, My, Mz, Qy, Qz, Mx). RU: Задать усилия узла.
- **idea_start_service**() — Запустить REST-сервис IDEA StatiCa Connection (автопоиск установки). Нужен IDEA StatiCa v24+.
- **idea_status**() — KK: Барлық узелдердің жиынтық есебі (Unity Check, OK/FAIL). RU: Сводка по всем узлам.
- **idea_stop_service**() — KK: REST сервисін тоқтату (exe-ді жабу). RU: Остановить REST-сервис. EN: Stop the REST service / kill the exe.

## autocad* (9)
- **autocad_draw_kj**(design, output_dir, dry_run) — KK: Дизайн нәтижесінен (lira_to_rebar_design бір элементі) ҚАБАТТЫ КЖ сызба — ARMAT_BOT/TOP/
- **autocad_execute**(command) — Выполнить любую команду AutoCAD через COM SendCommand. Нужен STRUCTOS_AUTOCAD_ENABLE_EXEC.
- **autocad_ezdxf_read**(path) — Прочитать .dxf С ДИСКА через ezdxf — AutoCAD НЕ обязателен. Авто-детект осей, отметок
- **autocad_lira**() — AutoCAD→LIRA: линии слоёв КОЛОННЫ/БАЛКИ → payload узлов+стержней LIRA.
- **autocad_read**(layers, entity_types) — Прочитать все объекты из открытого DWG (размеры, слои, блоки, текст, полилинии).
- **autocad_read_axes**(name_filter) — Найти оси (А-Я / 1-32) с координатами — БЕЗ explode, читая определения блоков на месте.
- **autocad_read_blocks**() — Прочитать ВСЕ блоки (INSERT) — сырьё: {name, insertion, rotation, scale, attributes}.
- **autocad_read_filtered**(entity_types, layers, max_entities) — Быстро прочитать из открытого DWG ТОЛЬКО указанные типы объектов (фильтр SelectionSet)
- **autocad_read_levels**() — Прочитать ВСЕ TEXT/MTEXT из открытого чертежа в сыром виде — {text, x, y, z}. Без фильтрации.

## structos* (8)
- **structos_clear_tasks**() — KK: Аяқталған (done/failed) тапсырмаларды тазалау (running қалады). RU: Очистить завершённые задачи.
- **structos_get_tasks**(limit) — KK: Фондық тапсырмалар тізімін қайтару (running/done/failed) — UI панелі үшін. RU: Список фоновых
- **structos_intent**(text) — Классифицировать команду на естественном языке в intent StructOS (сначала regex, при неуверенности
- **structos_model_diff**(source_a, source_b, ifc_path_a, ifc_path_b) — Сравнить две модели (по типам, совпавшие/несовпавшие элементы). EN: Diff two models (counts by
- **structos_read_model**(source, ifc_path) — KK: StructOS біртұтас объект моделін оқу — 'lira'|'tekla'|'ifc' көзінен bars+nodes (мм) моделін
- **structos_run_pipeline**(description, to_tekla, build, dwg_path, floors, height, material) — Полный пайплайн: (чертёж АР DWG/DXF или ЕЯ) → LIRA → Tekla КМ → AutoCAD КЖ. dwg_path строит из сетки осей.
- **structos_status**() — Проверить, какие программы (LIRA/Tekla/AutoCAD/Revit) сейчас запущены + здоровье мостов.
- **structos_sync_model**(source, target, dry_run, ifc_path) — Сопоставить модели двух программ по геометрии, вернуть % совпадения и связь ID.

## template* (6)
- **template_apply**(template_id, new_forces) — KK: Шаблонды ЖАҢА жүктемеге қолдану — сол қимаға new_forces (M_bot/M_top/Q) бойынша қайта
- **template_generate_standard**() — KK: Стандарт шаблондар генерациясы (seed) — ~200+ балка/плита/колонна/іргетас (B25/B30/B35,
- **template_get**(template_id) — KK: ID бойынша шаблон алу (usage_count++). Мыс. template_id="Б_300x500_B25_A400". Толық
- **template_save_from_lira**(element_id, element_type, geometry, rebar_result, concrete_class, rebar_class, project, tags, quantities) — KK: LIRA/kj есеп нәтижесінен ЖАҢА шаблон жасап кітапханаға сақтайды (жобадан нақты есеп→шаблон).
- **template_search**(element_type, b_mm, h_mm, concrete_class, rebar_class, tags) — KK: КЖ шаблон КІТАПХАНАСЫНАН іздеу (PKPM стилі — бір рет есептелген→қайта қолдану). element_type
- **template_stats**() — KK: Кітапхана статистикасы — жалпы саны, тип бойынша, ең көп қолданылған, жалпы арматура кг.

## ifc* (3)
- **ifc_read**(path, members) — Прочитать IFC через IfcOpenShell — схема, проект, единицы, счёт элементов + члены
- **ifc_to_fem**(ifc_path, make_synthetic) — IFC4 → каркасная FEM-модель (узлы/элементы) через ifcopenshell — независимо от исходников
- **ifc_to_opensees**(ifc_path, analyze) — KK: IFC файлын OpenSees каркас моделіне айналдыру — IfcBeam/IfcColumn/IfcMember мүшелерінің

## dwg* (3)
- **dwg_build_from_analysis**(analysis, floors, material, build, solve) — Построить каркас КЭ10 LIRA из JSON-анализа, который ЭТОТ ЧАТ получил из дайджеста; build/solve
- **dwg_read_export_digest**(export_path) — Прочитать экспорт C#-плагина, вернуть компактный дайджест + вопрос инженера — анализирует ЭТОТ
- **dwg_to_lira**(path, floors, height, material, live_kpa, snow_kpa, solve) — DWG/DXF → LIRA: сетка из осей (колонны) → каркас КЭ10 через lira_model_gen; solve → расчёт.

## normatives* (3)
- **normatives_get**(code) — Получить полный индексированный текст конкретного норматива (по коду).
- **normatives_search**(query, k) — Поиск по локальной библиотеке нормативов по ключевым словам (СП РК/Еврокод/ГОСТ PDF).
- **normatives_sp_rk_loads**(description, building_type) — Извлечь нагрузки из текста запроса (снег/ветер/сейсмика/полезная) — БЕЗ hardcode по городу.

## rebar* (2)
- **rebar_solve**(element, dry_run) — KK: Балка арматурасын ІРІКТЕУ солвері (OR-Tools CP-SAT): талап етілген As (см², қима бойынша) →
- **rebar_weight_calc**(design, output_dir, dry_run) — KK: Арматура ВЕДОМОСТІ (болат шығыны): әр позиция ⌀/ұзындық/сан/масса + диаметр бойынша

## opensees* (2)
- **opensees_analyze**(E, A, L, P, I, direction) — Расчёт одноэлементной консоли через OpenSeesPy — перемещение конца + реакции опоры, с
- **opensees_visualize**(result, output_path) — Визуализация результата OpenSees через opstool — эпюра моментов (или осевых) + деформированная

## spec* (1)
- **spec_generate**(elements, project_name) — KK: Сводная спецификация арматуры (ГОСТ 21.101) в Excel — 3 листа: спецификация изделий, ведомость

## sap2000* (1)
- **sap2000_read_forces**(load_cases, load_combinations, group_name) — Прочитать усилия рам (frame) открытой модели SAP2000 — таблица "Element Forces - Frames"

## pynite* (1)
- **pynite_verify_member**(section, N_kN, Vz_kN, My_kNm, grade, E, length_m) — НЕЗАВИСИМАЯ верификация усилий одного элемента LIRA через PyNite. Строит малую PyNite-модель

## building* (1)
- **building_generate_full**(text, dry_run) — KK: Мәтіннен ТОЛЫҚ ғимаратты ЛИРА + Tekla екеуінде бірден жасау (офлайн, dry_run). RU: Сгенерировать

## handcalcs* (1)
- **handcalcs_generate_report**(N_kN, My_kNm, A_cm2, Wx_cm3, Vz_kN, grade, title) — Сгенерировать LaTeX-отчёт проверки элемента через handcalcs — напряжение σ=N/A+My/Wx и

## anastruct* (1)
- **anastruct_frame_analyze**(length, EI, q, left_support, right_support, EA, point_loads) — Быстрый 2D-расчёт однопролётного ригеля/балки через anaStruct — момент/сдвиг/реакции/прогиб.

## read* (1)
- **read_dwg_file**(path, layers, entity_types) — Прочитать DWG/DXF ПРЯМО с диска (AutoCAD не нужен) — слои, линии, блоки (оси!), тексты, размеры.

## nonlinear* (1)
- **nonlinear_analyze**(node_x, area_mm2, E_MPa, sig_y_MPa, H_MPa, tip_force_N, n_steps) — KK: Материал нелинейлігі бар осьтік стерженьді Newton-Raphson-мен есептеу (тәуелсіз,

## section* (1)
- **section_properties**(shape, h, b, tw, tf, points, dxf_path) — Свойства сечения (A, Ix, Iy, Wx, Wy, rx, ry) полигональными формулами (подход