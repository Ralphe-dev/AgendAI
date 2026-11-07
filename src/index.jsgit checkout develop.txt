// AgendAI - Motor Principal

let compromissos = [];

// Função para adicionar com validação de horário
function adicionarCompromisso(titulo, data, hora) {
    const conflito = compromissos.find(c => c.data === data && c.hora === hora);
    
    if (conflito) {
        console.log(`[ERRO] O horário ${hora} no dia ${data} já está ocupado!`);
        return;
    }

    compromissos.push({ titulo, data, hora });
    console.log(`[SUCESSO] "${titulo}" agendado para ${data} às ${hora}.`);
}

// Função para listar
function listarCompromissos() {
    console.log("\n--- Meus Compromissos ---");
    if (compromissos.length === 0) {
        console.log("Nenhuma agenda encontrada.");
    } else {
        compromissos.forEach(c => console.log(`${c.data} às ${c.hora} - ${c.titulo}`));
    }
    console.log("-------------------------\n");
}

// Executando o sistema
console.log("Iniciando AgendAI...\n");
adicionarCompromisso("Reunião de Projeto", "10/11/2026", "14:00");
adicionarCompromisso("Dentista", "10/11/2026", "16:00");
adicionarCompromisso("Cliente X (Conflito)", "10/11/2026", "14:00"); // Vai ser bloqueado

listarCompromissos();