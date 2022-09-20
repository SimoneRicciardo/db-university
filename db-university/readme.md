<!-- EX - Query con GROUP BY -->

1. Contare quanti iscritti ci sono stati ogni anno

Soluzione 1 :   SELECT COUNT(*) AS "studenti_per_anno", 
                YEAR(`enrolment_date`) AS "anni" 
                FROM `students` 
                GROUP BY YEAR(`enrolment_date`);


2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

Soluzione 2 :   SELECT COUNT(`id`) AS "numero_insegnanti", (`office_address`) AS "uffici"
                FROM `teachers`
                WHERE `office_address` = `office_address`
                GROUP BY (`office_address`);


3. Calcolare la media dei voti di ogni appello d'esame

Soluzione 3 :   SELECT COUNT(`exam_id`) AS "appello_n",
                AVG(`vote`) AS "media_dei_voti"
                FROM `exam_student`
                GROUP BY (`exam_id`)


4. Contare quanti corsi di laurea ci sono per ogni dipartimento

Soluzione 4 :   SELECT (`department_id`) AS "dipartimento_n", COUNT(`name`) AS "corso_di_laurea"
                FROM `degrees`
                GROUP BY (`department_id`);




<!-- EX - Query con SELECT -->

1. Selezionare tutti gli studenti nati nel 1990 (160)

Soluzione 1 :   SELECT *
                FROM `students` 
                WHERE YEAR (`date_of_birth`) = "1990";


2. Selezionare tutti i corsi che valgono più di 10 crediti (479)

Soluzione 2 :   SELECT * 
                FROM `courses` 
                WHERE `cfu` > "10";


3. Selezionare tutti gli studenti che hanno più di 30 anni

Soluzione 3 :   SELECT * 
                FROM `students` 
                WHERE 1 YEAR (`date_of_birth`) <= "1992";


4. Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)

Soluzione 4 :   SELECT *
                FROM `courses` 
                WHERE `period` = "I semestre" 
                AND `year` = "1";


5. Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)

Soluzione 5 :   SELECT * 
                FROM `exams` 
                WHERE HOUR (`hour`) >= "14"
                AND `date` = "2020/06/20";  


6. Selezionare tutti i corsi di laurea magistrale (38)

Soluzione 6 :   SELECT * 
                FROM `degrees` 
                WHERE `name` LIKE "%Magistrale%";


7. Da quanti dipartimenti è composta l'università? (12)

Soluzione 7 :   SELECT COUNT(`id`) AS "n_dipartimenti" 
                FROM `departments


8. Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

Soluzione 8 :   SELECT * 
                FROM `teachers` 
                WHERE `phone` <> "NULL";
