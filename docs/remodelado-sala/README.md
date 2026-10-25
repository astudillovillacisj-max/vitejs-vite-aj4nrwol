# Remodelado sala-comedor (para /banana)

- `brief.json`: brief `banana.visual-brief.v1` ya autorizado por el usuario (foto propia, envío a Google permitido, uso privado, retrato retirado).
- `prompt.txt`: prompt exacto del plan (hash sha256 `4f51afc9...cf48fb`).

Para ejecutar, en una sesión con `GEMINI_API_KEY` configurada y la foto original adjunta:

    python3 .claude/skills/banana/scripts/edit.py --image FOTO.jpg \
      --reference-name "foto actual de la sala-comedor" --reference-role object \
      --reference-purpose "conservar la geometría, perspectiva, piso, techo con molduras y distribución del espacio" \
      --reference-subject-id sala-comedor --brief-file docs/remodelado-sala/brief.json \
      --prompt "$(cat docs/remodelado-sala/prompt.txt)" \
      --model gemini-nano-banana-2.1 --aspect-ratio 3:4 --resolution 1K

Sin `--execute` solo planea. Mostrar el plan y pedir aprobación antes de ejecutar con `--execute --confirm ID`.
