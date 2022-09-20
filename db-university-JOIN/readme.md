1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

Soluzione 1 :   SELECT *
                FROM `students`
                JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
                WHERE `degrees`.`name`= "Corso di Laurea in Economia";


2. Selezionare tutti i Corsi di Laurea del Dipartimento di Neuroscienze

Soluzione 2 :   SELECT * 
                FROM `degrees`
                JOIN `departments` ON `degrees`.`department_id`=`departments`.`id`
                WHERE `degrees`.`department_id`= "7"; (?)


3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

Soluzione 3 :   SELECT `teacher_id` AS "id_insegnante", `teachers`.`name`, `teachers`. `surname` ,`courses`.`id` AS "id_corso", `courses`.`name`
                FROM `course_teacher` 
                JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`
                JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
                WHERE `teacher_id` = "44";


4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

Soluzione 4 :   SELECT * 
                FROM `students`
                JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
                JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
                ORDER BY `students`.`surname`, `students`.`name` ASC;


5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

Soluzione 5 :   SELECT * 
                FROM `degrees`
                JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id`
                JOIN `course_teacher` ON `courses`.`id`=`course_teacher`.`teacher_id`
                JOIN `teachers` ON `course_teacher`.`course_id`=`teachers`.`id`;


6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

Soluzione 1 :


7. BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per superare ciascuno dei suoi esami

Soluzione 1 :



SELECT degrees.id AS "degree_id", period, courses.name, year 
FROM degrees 
JOIN courses ON courses.degree_id = degrees.id 
WHERE degrees.name = "Corso di Laurea in Informatica";