# SQL_em_Projeto_Real_Mini_mundo_Clinica_Veterinaria

-----------------------------------
-- INSERTS
-----------------------------------
-- Inserção de Tutores
INSERT INTO Tutor (id_tutor, nome, telefone, email)
VALUES
(1, 'Maria Oliveira', '11988887777', 'maria@gmail.com'),
(2, 'João Santos', '11955554444', 'joao@gmail.com'),
(3, 'Carla Almeida', '11933332222', 'carla@gmail.com');

-- Inserção de Animais
INSERT INTO Animal (id_animal, nome, especie, raca, idade, id_tutor)
VALUES
(1, 'Rex', 'Cachorro', 'Labrador', 5, 1),
(2, 'Mia', 'Gato', 'Siamês', 2, 2),
(3, 'Thor', 'Cachorro', 'Pastor Alemão', 4, 1),
(4, 'Luna', 'Gato', 'Vira-lata', 1, 3);

-- Inserção de Veterinários
INSERT INTO Veterinario (id_vet, nome, especialidade, crmv)
VALUES
(1, 'Dr. Pedro Lima', 'Clínico Geral', '12345-SP'),
(2, 'Dra. Ana Ribeiro', 'Dermatologia', '67890-SP');

-- Inserção de Serviços
INSERT INTO Servico (id_servico, nome, preco)
VALUES
(1, 'Consulta Geral', 120.00),
(2, 'Vacinação', 80.00),
(3, 'Exame de Sangue', 150.00);

-- Inserção de Consultas
INSERT INTO Consulta (id_consulta, data_consulta, id_vet, id_animal, id_servico, observacoes)
VALUES
(1, '2025-02-01', 1, 1, 1, 'Animal saudável.'),
(2, '2025-02-05', 2, 2, 2, 'Vacinação anual aplicada.'),
(3, '2025-02-10', 1, 3, 3, 'Exame solicitado por alteração de comportamento.'),
(4, '2025-03-01', 1, 1, 1, 'Revisão – tudo normal.');



-----------------------------------
-- SELECTS
-----------------------------------
-- 1. Listar todos os animais com seus tutores
SELECT 
    a.nome AS animal,
    a.especie,
    t.nome AS tutor
FROM Animal a
JOIN Tutor t ON a.id_tutor = t.id_tutor
ORDER BY a.nome;

-- 2. Consultas realizadas em fevereiro de 2025
SELECT 
    c.id_consulta,
    c.data_consulta,
    v.nome AS veterinario,
    a.nome AS animal
FROM Consulta c
JOIN Veterinario v ON c.id_vet = v.id_vet
JOIN Animal a ON c.id_animal = a.id_animal
WHERE c.data_consulta BETWEEN '2025-02-01' AND '2025-02-28'
ORDER BY c.data_consulta;

-- 3. Animais da espécie "Cachorro"
SELECT * FROM Animal
WHERE especie = 'Cachorro';

-- 4. Veterinários ordenados por especialidade
SELECT * FROM Veterinario
ORDER BY especialidade;

-- 5. Top 3 serviços mais caros
SELECT * FROM Servico
ORDER BY preco DESC
LIMIT 3;


-----------------------------------
-- UPDATES
-----------------------------------

-- 1. Atualizar telefone de um tutor
UPDATE Tutor
SET telefone = '11900001111'
WHERE id_tutor = 1;

-- 2. Ajustar preço de um serviço
UPDATE Servico
SET preco = preco + 20
WHERE id_servico = 1;

-- 3. Alterar observações de uma consulta
UPDATE Consulta
SET observacoes = 'Retorno agendado para 30 dias.'
WHERE id_consulta = 3;

-----------------------------------
-- DELETES
-----------------------------------

-- 1. Remover uma consulta antiga
DELETE FROM Consulta
WHERE id_consulta = 4;

-- 2. Remover um serviço que não é mais oferecido
DELETE FROM Servico
WHERE id_servico = 2;

-- 3. Excluir um animal (somente possível se não tiver FK pendente)
DELETE FROM Animal
WHERE id_animal = 4;
